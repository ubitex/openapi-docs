Sure! Here's the English translation of the API documentation:

---

## REST API

> `Domain`: `http://api.ubit.site`

----

## Basic Information

Due to high latency and poor stability, accessing the API through a proxy is not recommended.

For GET requests, parameters should be included in the query params; for POST requests, parameters should be included in the request body.

Set the request header to: `Content-Type=application/json`

For requests other than those starting with `/public`, you need to sign the request payload.

----

## Rate Limiting Rules

Some interfaces have rate limiting (details are specified under each interface). Rate limiting primarily consists of gateway rate limiting and WAF rate limiting.

If an API request triggers gateway rate limiting, it will return `429`, indicating that the access frequency is exceeded and the IP or apiKey may be banned.

Gateway rate limiting is divided into IP rate limiting and apiKey rate limiting.

IP rate limiting example: `100/s/ip`, meaning each IP is limited to a specific number of requests per second for that interface.

apiKey rate limiting example: `50/s/apiKey`, meaning each apiKey is limited to a specific number of requests per second for that interface.

----

## Signature Explanation

To ensure data security for UbitEx's open APIs, including protection against data tampering, data expiration, data replay, and access frequency issues, a request signature is required.

1. Apply for `appkey` and `secretkey` through the user center. Different `appkey` and `secretkey` should be used for different calls.

2. Add `timestamp` (the UNIX timestamp in milliseconds of when the request is sent) to the request.

3. Add `signature` (the data signature) to the request.

4. Add `recvwindow` (custom request validity period), which is currently fixed at a certain value.

   > The server will check the timestamp in the request. Requests sent more than 5000 milliseconds ago will be considered invalid. The effective time window can be set using the optional parameter `recvWindow`. If the timestamp is more than 1 second in the future, the request will be rejected. For high-frequency trading, you may adjust the `recvwindow` to meet your timing requirements. It is not recommended to use a `recvwindow` greater than 5 seconds.

5. Add `algorithms` (signature method/algorithm), where the signature is based on hashing. The recommended algorithm is HmacSHA256. Supported algorithms include:
   `HmacMD5, HmacSHA1, HmacSHA224, HmacSHA256 (recommended), HmacSHA384, HmacSHA512`.

### Signature Generation

For example, with `http://api.ubit.site/v1/spot`:
Here’s how you can use `echo`, `openssl`, and `curl` in a Linux bash environment to call an API for placing an order:

Example `appKey` and `secret`:

- `appKey`: uasdfk-76d0-4f6e-a6b2-asdfdas
- `secretKey`: bc6630d0231fda5cd98794f52c4998659beda290

Header Data:

- `validate-algorithms`: HmacSHA256
- `validate-appkey`: uasdfk-76d0-4f6e-a6b2-asdfdas
- `validate-recvwindow`: 5000
- `validate-timestamp`: 1717234493000
- `validate-signature`: 1231312318f13dc27dbbd02c2cc51ff7059765ed12313131

### Request Data

```json
{"symbol":"BTC_USDT","clientOrderId":"16559590087220001","side":"BUY","type":"LIMIT","timeInForce":"FOK","bizType":"SPOT","price":40000,"quantity":2}
```

#### 1. Data Section

- `method`: Request method in uppercase, e.g., GET, POST, DELETE, PUT
- `path`: Concatenate all values in the path in order. For RESTful paths like `/test/{var1}/{var2}/`, concatenate the actual parameters. Example: `/sign/test/bb/aa`
- `query`: Sort all key-value pairs by key in dictionary order and concatenate. Example: `userName=dfdfdf&password=ggg`
- `body`: Directly use the JSON string without conversion or sorting.

    - `x-www-form-urlencoded`: Sort all key-value pairs by key in dictionary order and concatenate. Example: `userName=dfdfdf&password=ggg`
    - `form-data`: This format is not supported.

  If multiple data formats are used, concatenate them in the order of path, query, and body to get the concatenated value.

Method example: POST
Path example: `/v1/spot/order`
Query parameters example: `symbol=btc_usdt`
Body example:
- `x-www-form-urlencoded`:
  ```
  symbol=btc_usdt&side=BUY&type=LIMIT&timeInForce=GTC&quantity=1&price=69000
  ```
- `json`:
  ```json
  {"symbol":"BTC_USDT","clientOrderId":"16559590087220001","side":"BUY","type":"LIMIT","timeInForce":"FOK","bizType":"SPOT","price":40000,"quantity":2,"media":"btok","mediaChannel":"12345"}
  ```

The concatenated value is represented as `Y=#method#path#query#body`.
Note:
- If `query` has data and `body` has no data: `Y=#method#path#query`
- If `query` has no data and `body` has data: `Y=#method#path#body`
- If both `query` and `body` have data: `Y=#method#path#query#body`

#### 2. Request Header Section

Concatenate the keys in alphabetical order using `&`, as `X`. Example:

> `validate-algorithms=HmacSHA256&validate-appkey=uasdfk-76d0-4f6e-a6b2-asdfdas&validate-recvwindow=5000&validate-timestamp=1641446237201`

#### 3. Generate Signature

Combine `X` and `Y` to get `original=XY`. Encrypt this string to get the signature.

```java
String signature=org.apache.commons.codec.digest.HmacUtils.hmacSha256Hex(secretkey, original);
```

Add the generated `signature` to the request header with `validate-signature` as the key.

#### 4. Example

- Signature raw message example:

> `validate-algorithms=HmacSHA256&validate-appkey=2fa91add-388c-44f2-8365-f4b72886c135&validate-recvwindow=6000&validate-timestamp=1725455266041#POST#/v1/spot/order#{"symbol":"BTC_USDT","clientOrderId":"16559590087220001","side":"BUY","type":"LIMIT","timeInForce":"FOK","bizType":"SPOT","price":40000,"quantity":2,"media":"btok","mediaChannel":"12345"}`

- Request example:

```shell
curl --location --request POST 'https://api.ubit.site/v1/spot/order' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725455266041' \
--header 'validate-signature: ce246607785e168d4677afff5af3746eb8513133d11ca3c5e3913eeea5aca63c' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' \
--data-raw '{"symbol":"BTC_USDT","clientOrderId":"16559590087220001","side":"BUY","type":"LIMIT","timeInForce":"FOK","bizType":"SPOT","price":40000,"quantity":2,"media":"btok","mediaChannel":"12345"}'
```

- Notes:
    - Ensure correct `Content-Type` and parameter formats in the raw signature message and request message.
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

----

## Response Codes

### HTTP Status

| httpStatus | Description                              |
|:-----------|:-----------------------------------------|
| 200        | Request successful, check rc, mc section |
| 404        | Interface not found                       |
| 429        | Request too frequent, control request rate |
| 500        | Service exception                        |
| 502        | Gateway exception                        |
| 503        | Service unavailable, please try again later |

### Result Code

| code | return Code |
|------|-------------|
| 0    | Business success |
| 1    | Business failure |

Here is the English translation for the provided content:

### Message Code

| msg          | message code                                |
|--------------|---------------------------------------------|
| SUCCESS      | Success                                      |
| FAILURE      | Failure                                      |
| AUTH_001     | Missing request header `validate-appkey`      |
| AUTH_002     | Missing request header `validate-timestamp`   |
| AUTH_003     | Missing request header `validate-recvwindow`  |
| AUTH_004     | Incorrect request header `validate-recvwindow` |
| AUTH_005     | Missing request header `validate-algorithms`  |
| AUTH_006     | Incorrect request header `validate-algorithms` |
| AUTH_007     | Missing request header `validate-signature`   |
| AUTH_101     | ApiKey does not exist                         |
| AUTH_102     | ApiKey not activated                          |
| AUTH_103     | Signature error                               |
| AUTH_104     | Request from unbound IP                       |
| AUTH_105     | Message outdated                              |
| AUTH_106     | Exceeds ApiKey permissions                    |
| SYMBOL_001   | Trading pair does not exist                   |
| SYMBOL_002   | Trading pair not open for trading             |
| SYMBOL_003   | Trading pair suspended                        |
| SYMBOL_004   | This trading pair is not supported in your country |
| SYMBOL_005   | This market does not support trading via API  |
| ORDER_001    | Platform order rejection                      |
| ORDER_002    | Insufficient funds                            |
| ORDER_003    | Trading pair suspended                        |
| ORDER_004    | Trading forbidden                             |
| ORDER_005    | Order does not exist                          |
| ORDER_006    | Too many open orders                          |
| ORDER_007    | Subaccount does not have trading permissions  |
| ORDER_008    | Current order price or quantity precision error |
| ORDER_F0101  | Trigger price filter - minimum value          |
| ORDER_F0102  | Trigger price filter - maximum value          |
| ORDER_F0103  | Trigger price filter - step value            |
| ORDER_F0201  | Trigger quantity filter - minimum value       |
| ORDER_F0202  | Trigger quantity filter - maximum value       |
| ORDER_F0203  | Trigger quantity filter - step value         |
| ORDER_F0301  | Trigger amount filter - minimum value         |
| ORDER_F0401  | Trigger opening protection filter             |
| ORDER_F0501  | Trigger limit protection filter - max deviation for buy orders |
| ORDER_F0502  | Trigger limit protection filter - max deviation for sell orders |
| ORDER_F0601  | Trigger market protection filter              |
| COMMON_001   | User does not exist                           |
| COMMON_002   | System busy, please try again later           |
| COMMON_003   | Operation failed, please try again later      |
| CURRENCY_001 | Currency information error                    |
| DEPOSIT_001  | Deposit not open                              |
| DEPOSIT_002  | Current account security level is low, please bind any two of phone/email/Google Authenticator for security verification before depositing |
| DEPOSIT_003  | Incorrect address format, please re-enter    |
| DEPOSIT_004  | Address already exists, please re-enter      |
| DEPOSIT_005  | Cold wallet address not found                |
| DEPOSIT_006  | No deposit address available, please try again later |
| DEPOSIT_007  | Address generation in progress, please try again later |
| DEPOSIT_008  | Deposit not supported                         |
| WITHDRAW_001 | Withdrawal not open                           |
| WITHDRAW_002 | Withdrawal address is invalid                 |
| WITHDRAW_003 | Current account security level is low, please bind any two of phone/email/Google Authenticator for security verification before withdrawing |
| WITHDRAW_004 | Withdrawal address not added                  |
| WITHDRAW_005 | Withdrawal address cannot be empty            |
| WITHDRAW_006 | Memo cannot be empty                          |
| WITHDRAW_008 | Risk control triggered, withdrawal of this currency not supported |
| WITHDRAW_009 | Withdrawal failed, some assets subject to T+1 withdrawal restrictions |
| WITHDRAW_010 | Withdrawal precision is invalid               |
| WITHDRAW_011 | Insufficient available balance                |
| WITHDRAW_012 | Withdrawal failed, remaining daily withdrawal limit insufficient |
| WITHDRAW_013 | Withdrawal failed, remaining daily withdrawal limit insufficient, increase limit by completing higher-level identity verification |
| WITHDRAW_014 | This withdrawal address cannot use internal transfer, please cancel internal transfer function before submitting |
| WITHDRAW_015 | Withdrawal amount insufficient to cover fees |
| WITHDRAW_016 | Withdrawal address already exists            |
| WITHDRAW_017 | This withdrawal has been processed, cannot be canceled |
| WITHDRAW_018 | Memo must be numeric                          |
| WITHDRAW_019 | Incorrect Memo, please re-enter               |
| WITHDRAW_020 | Daily withdrawal limit reached, please try again tomorrow |
| WITHDRAW_021 | Daily withdrawal limit reached, you can withdraw up to {0} |
| WITHDRAW_022 | Withdrawal amount must be greater than {0}   |
| WITHDRAW_023 | Withdrawal amount must be less than {0}      |
| WITHDRAW_024 | Withdrawal not supported                      |
| WITHDRAW_025 | Please create FIO address on the deposit page |
| FUND_001     | Duplicate request (multiple requests with the same bizId) |
| FUND_002     | Insufficient balance                          |
| FUND_003     | Transfer operation not supported (e.g., sub-accounts do not support fund transfers in or out) |
| FUND_004     | Unfreeze failed                               |
| FUND_005     | Transfer prohibited                           |
| FUND_014     | Transfer from and to account IDs cannot be the same |
| FUND_015     | `from` and `to` business types cannot be the same (users cannot transfer from spot to spot) |
| FUND_016     | Leverage trading pair cannot be empty         |
| FUND_017     | Parameter error                                |
| FUND_018     | Freeze record invalid                         |
| FUND_019     | Unfreeze user mismatch                        |
| FUND_020     | Unfreeze currency mismatch                    |
| FUND_021     | Operation not supported                       |
| FUND_022     | Freeze record amount exceeds maximum length of 113 |
| SYMBOL_001   | Trading pair does not exist                   |
| TRANSFER_001 | Duplicate request (multiple requests with the same bizId) |
| TRANSFER_002 | Insufficient balance                          |
| TRANSFER_003 | User not registered                           |
| TRANSFER_004 | Currency transfer not allowed                 |
| TRANSFER_005 | User currency transfer not allowed            |
| TRANSFER_006 | Transfer prohibited                           |
| TRANSFER_007 | Request timed out                             |
| TRANSFER_008 | Leverage transfer in error                    |
| TRANSFER_009 | Leverage transfer out error                   |
| TRANSFER_010 | Leverage zeroing transfer prohibited          |
| TRANSFER_011 | Leverage borrowing transfer prohibited        |
| TRANSFER_012 | Currency transfer prohibited                  |
| GATEWAY_0001 | Risk control triggered                         |
| GATEWAY_0002 | Risk control triggered                         |
| GATEWAY_0003 | Risk control triggered                         |
| GATEWAY_0004 | Risk control triggered                         |

----

## Public Modules

### Order Status Codes

| State            | Description                  |
|------------------|------------------------------|
| NEW              | New                          |
| PARTIALLY_FILLED | Partially filled             |
| FILLED           | Fully filled                 |
| CANCELED         | User canceled                |
| REJECTED         | Order failed                 |
| EXPIRED          | Expired (e.g., `time_in_force` cancellation or premium cancellation) |

### Order Types

| Type   | Description |
|--------|-------------|
| LIMIT  | Limit order |
| MARKET | Market order |

### Trading Pair Status

| State    | Description |
|----------|-------------|
| ONLINE   | Online      |
| OFFLINE  | Offline     |
| DELISTED | Delisted    |

### Validity Types

Defines how long an order remains valid

| TimeInForces | Description                                |
|--------------|--------------------------------------------|
| GTC          | Good 'Til Canceled, valid until filled     |
| IOC          | Immediate or Cancel, cancels portion not filled |
| FOK          | Fill or Kill, cancels if not fully filled  |
| GTX          | Good 'Til Cancelled, cancels if not added as a pending order |

### Deposit/Withdrawal Record Status Codes

| Status        | Description                             |
|---------------|-----------------------------------------|
| SUBMIT        | Withdrawal: Not frozen                  |
| REVIEW        | Withdrawal: Frozen, pending review      |
| AUDITED       | Withdrawal: Reviewed, sent to wallet, pending on-chain |
| AUDITED_AGAIN | Under review                            |
| PENDING       | Deposit/Withdrawal: On-chain            |
| SUCCESS       | Completed                                |
| FAIL          | Failed                                   |
| CANCEL        | Canceled                                 |

### BizType

| Status    | Description |
|-----------|-------------|
| SPOT      | Spot trading |
| FINANCE   | Finance     |
| FUTURES_U | Futures U-based |
| UB_CARD   | UB Card account |

### Buy/Sell Direction

| Status | Description |
|--------|-------------|
| BUY    | Buy         |
| SELL   | Sell        |

----

## FAQs

1. **Why is it that after multiple successful requests, subsequent requests are returned with 500 error codes?**

   This situation might be caused by server instability. We recommend you try sending requests again later. If the problem persists, please contact support.

2. **Why do I encounter an 'Invalid signature' error?**

   This error often results from an incorrect signature. Ensure that the concatenation order and hashing method are accurate. For further assistance, please refer to the documentation for details.

3. **Why am I getting 'Missing request header validate-appkey' error?**

   This means your request is missing the `validate-appkey` header. Please ensure all required headers are included in your request.

4. **Why does the request fail with a 429 status code?**

   A 429 status code indicates that the request rate limit has been exceeded. Please reduce the frequency of your requests.

5. **How can I avoid rate limiting?**

   Adhere to the rate limits specified in the API documentation. Consider using multiple apiKeys if you need to scale up your request volume.

6. **Can I change the signature algorithm?**

   Currently, the supported algorithms are HmacMD5, HmacSHA1, HmacSHA224, HmacSHA256, HmacSHA384, and HmacSHA512. Using HmacSHA256 is recommended.

7. **Why does the request fail with a 'Service unavailable' error?**

   This error indicates that the service is currently unavailable. Please try again later.

8. **What should I do if I encounter a 'Service error' response?**

   This typically indicates an issue on the server side. If the error persists, contact support for further assistance.


9. **AUTH_105: Message Outdated**

    When the server validates the request header parameters `validate-timestamp` (validTimeStamp) and `validate-recvwindow` (recvwindow), the following rules must be met: `dealTimeStamp` (server time when the request is processed, in milliseconds) - `validTimeStamp` < `recvwindow`. If this condition is not satisfied, `AUTH_105` will be returned. To avoid this error, it is recommended to set `validate-timestamp` to the time the request is sent, in milliseconds, and to set `validate-recvwindow` to a larger value.

----

## Support

Get support in our Telegram group: [UBitEx API Support Group](https://t.me/ubitex_api_support)
For inquiries, please consult our online customer service.