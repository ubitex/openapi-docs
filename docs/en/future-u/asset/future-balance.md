# Get User's Funds Information

`GET` /v1/future-u/user/compat/balance/list

## Request Parameters

| name             | location    | type      | required | Description    |
|----------------|-------|---------|----|-------|
| queryAccountId | query | integer | No  | 账户id	 |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/compat/balance/list?queryAccountId' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725689486038' \
--header 'validate-signature: f430ffd906378bd429e9086722adeaf4ba4208f015b3519d6c6e1eed952a6cbb' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
  "code": 0,
  "msg": "SUCCESS",
  "msgInfo": [],
  "data": [
    {
      "accountId": 45756045342,
      "userId": 45756045342,
      "coin": "usdt",
      "underlyingType": 2,
      "walletBalance": "2064.09753498",
      "openOrderMarginFrozen": "0",
      "isolatedMargin": "0",
      "crossedMargin": "922.217582",
      "amount": "469.86121898",
      "totalAmount": "1430.23560098",
      "convertBtcAmount": "0.03813263",
      "convertUsdtAmount": "2064.0975",
      "profit": "64.90736581",
      "notProfit": "-633.861934",
      "bonus": "0",
      "coupon": "0"
    }
  ]
}
```

