Here is the translated documentation into English:

---

> **Domain**: `http://api.ubit.site`

## Basic API Information

Due to high latency and instability, it is not recommended to access the API through a proxy.

For GET requests, parameters should be included in the query parameters. For POST requests, parameters should be included in the request body.

Set the request header as: `Content-Type=application/json`.

For requests starting with anything other than `/public`, you need to sign the request message.

## Rate Limiting Rules

Some interfaces are subject to rate limiting (specific rate limits are detailed per interface). Rate limiting is primarily divided into gateway rate limiting and WAF rate limiting.

If an interface request triggers gateway rate limiting, it will return a 429 status code, indicating that the access frequency has exceeded the limit and that IP or API key may soon be banned.

Gateway rate limiting can be applied to both IP and API key.

- **IP Rate Limiting Example**: `100/s/ip` means that each IP is limited to 100 requests per second for that interface.
- **API Key Rate Limiting Example**: `50/s/apiKey` means that each API key is limited to 50 requests per second for that interface.

## Signature Explanation

Since UbitEx needs to provide open interfaces to third-party platforms, it requires data security, such as whether the data has been tampered with, whether the data is outdated, whether data can be resubmitted, and the access frequency within a certain period. Data tampering is the most critical issue.

1. Obtain an `appkey` and `secretkey` from the user center. Different calls should use different `appkey` and `secretkey`.

2. Include a `timestamp` (Unix timestamp in milliseconds) which represents the request time. The data validity is based on this value.

3. Include `signature` (data signature), which is the signature information for all data.

4. Include `recvwindow` (custom request validity period). Currently, the validity period is fixed to a certain value.

   > The server will check the timestamp in the request. The maximum allowed difference is 60 seconds, and the minimum is 2 seconds. If the timestamp is older than 5000 milliseconds, the request will be considered invalid. This time window value can be set using the optional `recvWindow` parameter. Also, if the server calculates that the client’s timestamp is more than one second ahead of the server time, the request will be rejected.
   For high-frequency trading where timing is critical, adjust the `recvwindow` to meet your requirements. It is not recommended to use a `recvwindow` longer than 5 seconds.

5. Include `algorithms` (signature method/algorithm). The recommended method is HmacSHA256. Supported protocols include:
   `HmacMD5, HmacSHA1, HmacSHA224, HmacSHA256 (recommended), HmacSHA384, HmacSHA512`.

### Signature Generation

For example, with `http://api.ubit.site/v1/spot`:
Here is an example of how to call an API endpoint to place an order using `echo`, `openssl`, and `curl` in a Linux bash environment.

Example `appkey` and `secretkey`:

- `appKey`: `uasdfk-76d0-4f6e-a6b2-asdfdas`
- `secretKey`: `bc6630d0231fda5cd98794f52c4998659beda290`

Header data:

- `validate-algorithms`: HmacSHA256
- `validate-appkey`: uasdfk-76d0-4f6e-a6b2-asdfdas
- `validate-recvwindow`: 5000
- `validate-timestamp`: 1717234493000
- `validate-signature`: 1231312318f13dc27dbbd02c2cc51ff7059765ed12313131

### Request Data

```json
{ "type": "LIMIT", "timeInForce": "GTC", "side": "BUY", "symbol": "btc_usdt", "price": "69000", "quantity": "1" }
```

#### 1. Data Part

- **method**: The HTTP request method in uppercase, e.g., GET, POST, DELETE, PUT.

- **path**: Concatenate all values in the path in order. For RESTful paths like `/test/{var1}/{var2}/`, fill in the actual parameters and concatenate the path. Example: `/sign/test/bb/aa`.

- **query**: Concatenate all `key=value` pairs sorted by key in dictionary order. Example: `userName=dfdfdf&password=ggg`.

- **body**: Directly use the JSON string without conversion or sorting.

  `x-www-form-urlencoded`: Concatenate all `key=value` pairs sorted by key in dictionary order. Example: `userName=dfdfdf&password=ggg`.

  `form-data`: This format is not supported currently.

  For mixed use of query and body (in both form and JSON formats):

  `query`: `symbol=btc_usdt&side=BUY&type=LIMIT`.

  `body` (JSON format): `{"symbol":"btc_usdt","side":"BUY","type":"LIMIT"}`.

- The final string is constructed by concatenating `#method`, `#path`, `#query`, `#body` with `#` symbols.

#### 2. Request Header Part

Concatenate the keys in natural ascending order with `&` as separators, forming `X`.

Example:

```
validate-algorithms=HmacSHA256&validate-appkey=uasdfk-76d0-4f6e-a6b2-asdfdas&validate-recvwindow=5000&validate-timestamp=1641446237201
```

#### 3. Generate Signature

The final string to be encrypted is `original=XY`.

Generate the signature using:

```java
signature=org.apache.commons.codec.digest.HmacUtils.hmacSha256Hex(secretkey, original);
```

Place the generated signature in the request header as `validate-signature`, with the `signature` value.

#### 4. Example

- Signature Raw Message Example:  
  `validate-algorithms=HmacSHA256&validate-appkey=uasdfk-76d0-4f6e-a6b2-asdfdas&validate-recvwindow=60000&validate-timestamp=1666026215729#POST#/v1/spot/order/order#{"symbol":"BTC_USDT","side":"BUY","type":"LIMIT","timeInForce":"GTC","bizType":"SPOT","price":69000,"quantity":2}`

- Request Example:

```bash
curl --location --request POST 'http://api.ubit.site/v1/spot/order'
--header 'accept: */*'
--header 'Content-Type: application/json'
--header 'validate-algorithms: HmacSHA256'
--header 'validate-appkey: uasdfk-76d0-4f6e-a6b2-asdfdas'
--header 'validate-recvwindow: 60000'
--header 'validate-timestamp: 1717234493000'
--header 'validate-signature: 1231312318f13dc27dbbd02c2cc51ff7059765ed12313131'
--data-raw '{"symbol":"BTC_USDT","side":"BUY","type":"LIMIT","timeInForce":"GTC","bizType":"SPOT","price":69000,"quantity":2}'
```

- **Notes**:

    - Ensure correct `Content-Type` and parameter formats in the signature raw message and request message.
    - Java SDK: [http://git.ubit.site/backend/sdk-for-java.git](http://git.ubit.site/backend/sdk-for-java.git)

## Response Format

All interfaces return data in JSON format.

```json
{
  "code": 0,
  "data": {},
  "msg": "SUCCESS",
  "msgInfo": []
}
```

## Response Codes

### HTTP Status

| httpStatus | Description                          |
|------------|--------------------------------------|
| 200        | Request successful; check rc, mc parts |
| 404        | Interface not found                   |
| 429        | Request too frequent; control request rate according to limits |
| 500        | Service exception                     |
| 502        | Gateway exception                     |
| 503        | Service unavailable; try again later  |

### Result Code

| code | Return Code |
|------|-------------|
| 0    | Business success |
| 1    | Business failure |

### Message Code

| msg          | Message Code                                |
|--------------|---------------------------------------------|
| SUCCESS      | Success                                      |
| FAILURE      | Failure                                      |
| AUTH_001     | Missing request header validate-appkey       |
| AUTH_002     | Missing request header validate-timestamp    |
| AUTH_003     | Missing request header validate-recvwindow   |
| AUTH_004     | Invalid request header validate-recvwindow   |
| AUTH_005     | Missing request header validate-algorithms   |
| AUTH_006     | Invalid request header validate-algorithms   |
| AUTH_007     | Missing request header validate-signature    |
| AUTH_101     | ApiKey does not exist                        |
| AUTH_102     | ApiKey not activated                         |
| AUTH_103     | Signature error                              |
| AUTH_104     | Unbound IP request                           |
| AUTH_105     | Message outdated                             |
| AUTH_106     | Exceeds apikey permission                    |
| SYMBOL_001   | Trading pair does not exist                  |
| SYMBOL_002   | Trading