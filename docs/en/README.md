## REST API

> **Domain**: `http://api.ubit.site`

## Basic API Information

Due to high latency and instability, it is not recommended to access the API through a proxy.

For GET requests, parameters should be included in the query parameters. For POST requests, parameters should be
included in the request body.

Set the request header as: `Content-Type=application/json`.

For requests starting with anything other than `/public`, you need to sign the request message.

## Rate Limiting Rules

Some interfaces are subject to rate limiting (specific rate limits are detailed per interface). Rate limiting is
primarily divided into gateway rate limiting and WAF rate limiting.

If an interface request triggers gateway rate limiting, it will return a 429 status code, indicating that the access
frequency has exceeded the limit and that IP or API key may soon be banned.

Gateway rate limiting can be applied to both IP and API key.

- **IP Rate Limiting Example**: `100/s/ip` means that each IP is limited to 100 requests per second for that interface.
- **API Key Rate Limiting Example**: `50/s/apiKey` means that each API key is limited to 50 requests per second for that
  interface.

## Signature Explanation

Since UbitEx needs to provide open interfaces to third-party platforms, it requires data security, such as whether the
data has been tampered with, whether the data is outdated, whether data can be resubmitted, and the access frequency
within a certain period. Data tampering is the most critical issue.

1. Obtain an `appkey` and `secretkey` from the user center. Different calls should use different `appkey` and
   `secretkey`.

2. Include a `timestamp` (Unix timestamp in milliseconds) which represents the request time. The data validity is based
   on this value.

3. Include `signature` (data signature), which is the signature information for all data.

4. Include `recvwindow` (custom request validity period). Currently, the validity period is fixed to a certain value.

   > The server will check the timestamp in the request. The maximum allowed difference is 60 seconds, and the minimum
   is 2 seconds. If the timestamp is older than 5000 milliseconds, the request will be considered invalid. This time
   window value can be set using the optional `recvWindow` parameter. Also, if the server calculates that the client’s
   timestamp is more than one second ahead of the server time, the request will be rejected.
   For high-frequency trading where timing is critical, adjust the `recvwindow` to meet your requirements. It is not
   recommended to use a `recvwindow` longer than 5 seconds.

5. Include `algorithms` (signature method/algorithm). The recommended method is HmacSHA256. Supported protocols include:
   `HmacMD5, HmacSHA1, HmacSHA224, HmacSHA256 (recommended), HmacSHA384, HmacSHA512`.

### Signature Generation

For example, with `http://api.ubit.site/v1/spot`:
Here is an example of how to call an API endpoint to place an order using `echo`, `openssl`, and `curl` in a Linux bash
environment.

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
{
  "type": "LIMIT",
  "timeInForce": "GTC",
  "side": "BUY",
  "symbol": "btc_usdt",
  "price": "69000",
  "quantity": "1"
}
```

#### 1. Data Part

- **method**: The HTTP request method in uppercase, e.g., GET, POST, DELETE, PUT.

- **path**: Concatenate all values in the path in order. For RESTful paths like `/test/{var1}/{var2}/`, fill in the
  actual parameters and concatenate the path. Example: `/sign/test/bb/aa`.

- **query**: Concatenate all `key=value` pairs sorted by key in dictionary order. Example:
  `userName=dfdfdf&password=ggg`.

- **body**: Directly use the JSON string without conversion or sorting.

  `x-www-form-urlencoded`: Concatenate all `key=value` pairs sorted by key in dictionary order. Example:
  `userName=dfdfdf&password=ggg`.

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

| httpStatus | Description                                                    |
|------------|----------------------------------------------------------------|
| 200        | Request successful; check rc, mc parts                         |
| 404        | Interface not found                                            |
| 429        | Request too frequent; control request rate according to limits |
| 500        | Service exception                                              |
| 502        | Gateway exception                                              |
| 503        | Service unavailable; try again later                           |

### Result Code

| code | Return Code      |
|------|------------------|
| 0    | Business success |
| 1    | Business failure |

Here's the translation of the document into English:

---

### Message Code

| msg          | message code                                                                                                                                       |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| SUCCESS      | Success                                                                                                                                            |
| FAILURE      | Failure                                                                                                                                            |
| AUTH_001     | Missing request header `validate-appkey`                                                                                                           |
| AUTH_002     | Missing request header `validate-timestamp`                                                                                                        |
| AUTH_003     | Missing request header `validate-recvwindow`                                                                                                       |
| AUTH_004     | Invalid request header `validate-recvwindow`                                                                                                       |
| AUTH_005     | Missing request header `validate-algorithms`                                                                                                       |
| AUTH_006     | Invalid request header `validate-algorithms`                                                                                                       |
| AUTH_007     | Missing request header `validate-signature`                                                                                                        |
| AUTH_101     | ApiKey does not exist                                                                                                                              |
| AUTH_102     | ApiKey not activated                                                                                                                               |
| AUTH_103     | Signature error                                                                                                                                    |
| AUTH_104     | Request from non-bound IP                                                                                                                          |
| AUTH_105     | Request is outdated                                                                                                                                |
| AUTH_106     | Exceeds ApiKey permissions                                                                                                                         |
| SYMBOL_001   | Trading pair does not exist                                                                                                                        |
| SYMBOL_002   | Trading pair not open                                                                                                                              |
| SYMBOL_003   | Trading pair suspended                                                                                                                             |
| SYMBOL_004   | This trading pair is not supported in your country                                                                                                 |
| SYMBOL_005   | The market does not support API trading                                                                                                            |
| ORDER_001    | Platform rejected the order                                                                                                                        |
| ORDER_002    | Insufficient funds                                                                                                                                 |
| ORDER_003    | Trading pair suspended                                                                                                                             |
| ORDER_004    | Trading prohibited                                                                                                                                 |
| ORDER_005    | Order does not exist                                                                                                                               |
| ORDER_006    | Too many unfilled orders                                                                                                                           |
| ORDER_007    | Subaccount has no trading permissions                                                                                                              |
| ORDER_008    | Current order price or quantity precision is abnormal                                                                                              |
| ORDER_F0101  | Trigger price filter - minimum value                                                                                                               |
| ORDER_F0102  | Trigger price filter - maximum value                                                                                                               |
| ORDER_F0103  | Trigger price filter - step value                                                                                                                  |
| ORDER_F0201  | Trigger quantity filter - minimum value                                                                                                            |
| ORDER_F0202  | Trigger quantity filter - maximum value                                                                                                            |
| ORDER_F0203  | Trigger quantity filter - step value                                                                                                               |
| ORDER_F0301  | Trigger amount filter - minimum value                                                                                                              |
| ORDER_F0401  | Trigger open protection filter                                                                                                                     |
| ORDER_F0501  | Trigger limit protection filter - maximum deviation for buy orders                                                                                 |
| ORDER_F0502  | Trigger limit protection filter - maximum deviation for sell orders                                                                                |
| ORDER_F0601  | Trigger market protection filter                                                                                                                   |
| COMMON_001   | User does not exist                                                                                                                                |
| COMMON_002   | System busy, please try again later                                                                                                                |
| COMMON_003   | Operation failed, please try again later                                                                                                           |
| CURRENCY_001 | Currency information error                                                                                                                         |
| DEPOSIT_001  | Deposits are not open yet                                                                                                                          |
| DEPOSIT_002  | Current account security level is too low, please bind any two of phone/email/Google Authenticator before depositing                               |
| DEPOSIT_003  | Address format is incorrect, please re-enter                                                                                                       |
| DEPOSIT_004  | Address already exists, please re-enter                                                                                                            |
| DEPOSIT_005  | Cold wallet address not found                                                                                                                      |
| DEPOSIT_006  | No deposit address available, please try again later                                                                                               |
| DEPOSIT_007  | Address generation in progress, please try again later                                                                                             |
| DEPOSIT_008  | Deposits not supported                                                                                                                             |
| WITHDRAW_001 | Withdrawals are not open yet                                                                                                                       |
| WITHDRAW_002 | Withdrawal address is invalid                                                                                                                      |
| WITHDRAW_003 | Current account security level is too low, please bind any two of phone/email/Google Authenticator before withdrawing                              |
| WITHDRAW_004 | Withdrawal address not added                                                                                                                       |
| WITHDRAW_005 | Withdrawal address cannot be empty                                                                                                                 |
| WITHDRAW_006 | Memo cannot be empty                                                                                                                               |
| WITHDRAW_008 | Risk control triggered, withdrawal of this coin is not supported                                                                                   |
| WITHDRAW_009 | Withdrawal failed, part of the assets in this withdrawal is subject to T+1 withdrawal restrictions                                                 |
| WITHDRAW_010 | Withdrawal precision is invalid                                                                                                                    |
| WITHDRAW_011 | Insufficient available balance                                                                                                                     |
| WITHDRAW_012 | Withdrawal failed, insufficient remaining withdrawal quota for today                                                                               |
| WITHDRAW_013 | Withdrawal failed, insufficient remaining withdrawal quota for today. You can increase the quota by completing higher-level real-name verification |
| WITHDRAW_014 | This withdrawal address cannot use internal transfer function, please cancel internal transfer function and resubmit                               |
| WITHDRAW_015 | Withdrawal amount is not sufficient to cover fees                                                                                                  |
| WITHDRAW_016 | Withdrawal address already exists                                                                                                                  |
| WITHDRAW_017 | This withdrawal has been processed and cannot be canceled                                                                                          |
| WITHDRAW_018 | Memo must be numeric                                                                                                                               |
| WITHDRAW_019 | Incorrect Memo, please re-enter                                                                                                                    |
| WITHDRAW_020 | Your withdrawal limit for today has been reached, please try again tomorrow                                                                        |
| WITHDRAW_021 | Your withdrawal limit for today has been reached, the maximum you can withdraw this time is {0}                                                    |
| WITHDRAW_022 | Withdrawal amount must be greater than {0}                                                                                                         |
| WITHDRAW_023 | Withdrawal amount must be less than {0}                                                                                                            |
| WITHDRAW_024 | Withdrawals not supported                                                                                                                          |
| WITHDRAW_025 | Please go to the deposit page to create a FIO address                                                                                              |
| FUND_001     | Duplicate request (same bizId requested multiple times)                                                                                            |
| FUND_002     | Insufficient balance                                                                                                                               |
| FUND_003     | Transfer operation not supported (e.g., subaccounts do not support fund transfers)                                                                 |
| FUND_004     | Unfreezing failed                                                                                                                                  |
| FUND_005     | Transfer prohibited                                                                                                                                |
| FUND_014     | Transfer from and to account ids cannot be the same                                                                                                |
| FUND_015     | `from` and `to` business types cannot be the same (users cannot transfer between their own spot accounts)                                          |
| FUND_016     | Leverage trading pair cannot be empty                                                                                                              |
| FUND_017     | Parameter error                                                                                                                                    |
| FUND_018     | Invalid freeze record                                                                                                                              |
| FUND_019     | Unfreeze user mismatch                                                                                                                             |
| FUND_020     | Unfreeze currency mismatch                                                                                                                         |
| FUND_021     | Operation not supported                                                                                                                            |
| FUND_022     | Freeze record amount exceeds the maximum length of 113                                                                                             |
| SYMBOL_001   | Trading pair does not exist                                                                                                                        |
| TRANSFER_001 | Duplicate request (same bizId requested multiple times)                                                                                            |
| TRANSFER_002 | Insufficient balance                                                                                                                               |
| TRANSFER_003 | User not registered                                                                                                                                |
| TRANSFER_004 | Currency transfer not allowed                                                                                                                      |
| TRANSFER_005 | User's currency transfer not allowed                                                                                                               |
| TRANSFER_006 | Transfer prohibited                                                                                                                                |
| TRANSFER_007 | Request timeout                                                                                                                                    |
| TRANSFER_008 | Leverage transfer in error                                                                                                                         |
| TRANSFER_009 | Leverage transfer out error                                                                                                                        |
| TRANSFER_010 | Leverage clearing out transfer prohibited                                                                                                          |
| TRANSFER_011 | Leverage with borrowing, transfer out prohibited                                                                                                   |
| TRANSFER_012 | Currency transfer prohibited                                                                                                                       |
| GATEWAY_0001 | Risk control triggered                                                                                                                             |
| GATEWAY_0002 | Risk control triggered                                                                                                                             |
| GATEWAY_0003 | Risk control triggered                                                                                                                             |
| GATEWAY_0004 | Risk control triggered                                                                                                                             |

## Common Modules

### Order Status Codes

| State            | Description                                |
|------------------|--------------------------------------------|
| NEW              | New                                        |
| PARTIALLY_FILLED | Partially filled                           |
| FILLED           | Fully filled                               |
| CANCELED         | User canceled                              |
| REJECTED         | Order failed                               |
| EXPIRED          | Expired (time_in_force or premium expired) |

### Order Types

| Type   | Description  |
|--------|--------------|
| LIMIT  | Limit order  |
| MARKET | Market order |

### Trading Pair Status

| State    | Description |
|----------|-------------|
| ONLINE   | Online      |
| OFFLINE  | Offline     |
| DELISTED | Delisted    |

### Time-in-Force Options

Defines how long an order remains valid.

| TimeInForces | Description                               |
|--------------|-------------------------------------------|
| GTC          | Good 'Til Canceled, valid until filled    |
| IOC          | Immediate Or Cancel, cancel unfilled part |
| FOK          | Fill Or Kill, cancel if not all filled    |
| GTX          | Good 'Til X, cancel if not a maker order  |

### Deposit/Withdrawal Record Status Codes

| Status        | Description                                         |
|---------------|-----------------------------------------------------|
| SUBMIT        | Withdrawal: Not frozen                              |
| REVIEW        | Withdrawal: Frozen, pending review                  |
| AUDITED       | Withdrawal: Reviewed, sent to wallet, pending chain |
| AUDITED_AGAIN | Under re-review                                     |
| PENDING       | Deposit/Withdrawal: On chain                        |
| SUCCESS       | Completed                                           |
| FAIL          | Failed                                              |
| CANCEL        | Canceled                                            |

### BizType

| Status    | Description          |
|-----------|----------------------|
| SPOT      | Spot                 |
| FINANCE   | Finance              |
| FUTURES_U | Futures (U-margined) |
| UB_CARD   | UB Card Account      |

### Buy/Sell Direction

| Status | Description |
|--------|-------------|
| BUY    | Buy         |
| SELL   | Sell        |

## FAQ

Here's the translation of the FAQ entry:

---

1. **AUTH_105**: When the server validates the request header parameters `validate-timestamp` (validTimeStamp) and
   `validate-recvwindow` (recvwindow), the following rule must be met: `dealTimeStamp` (the server time when the request
   is processed, in milliseconds) - `validTimeStamp` must be less than `recvwindow`. Otherwise, AUTH_105 will be
   returned. To avoid this error, it is recommended to set `validate-timestamp` to the time when the request is sent, in
   milliseconds, and to set `validate-recvwindow` to a larger value.