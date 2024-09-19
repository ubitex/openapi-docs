# Get User's Single Currency Fund Information

`GET` /v1/future-u/user/balance/detail

## Request Parameters

| name   | location    | type     | required | Description |
|------|-------|--------|----|----|
| coin | query | string | Yes  | coin |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/balance/detail?coin=usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514377041' \
--header 'validate-signature: 34f0fbb80feeb2246439bd65e14fed1ea5e5e63e79f9d7a57b2fe89b03e2c6b1' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=8FF5A9153450BDA558BF120CD75F0632'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": {
    "coin": "usdt",
    "walletBalance": "2499.57554469",
    "openOrderMarginFrozen": "0",
    "isolatedMargin": "0",
    "crossedMargin": "565.12545",
    "availableBalance": "1934.45009469",
    "bonus": "503",
    "coupon": "0"
  },
  "ts": 1725514377221
}
```

