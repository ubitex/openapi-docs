# Get a single currency asset

`GET` /v1/spot/balance

## Request Parameters

| name       | location    | type     | required | Description |
|----------|-------|--------|----|----|
| currency | query | string | No  | coin |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/balance?currency=USDT' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725534383748' \
--header 'validate-signature: e91e5d4d27d179606b618ae7c728390d32674c660008719cc8a6d09d772d694f' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": {
    "currency": "usdt",
    "currencyId": 11,
    "frozenAmount": "180534.40000000",
    "availableAmount": "8704106.23547842",
    "totalAmount": "8884640.63547842",
    "convertBtcAmount": "156.32640153",
    "convertUsdtAmount": "8884640.6354",
    "withdraw": null
  },
  "ts": 1725534383825
}
```

