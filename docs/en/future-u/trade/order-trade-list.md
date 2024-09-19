# Order Transaction Details

`GET` /v1/future-u/trade/order/trade-list

## Request Parameters

| name        | location    | type      | required | Description   |
|-----------|-------|---------|----|------|
| orderId   | query | integer | No  | 订单Id |
| symbol    | query | string  | No  | symbol  |
| startTime | query | integer | No  | 开始时间 |
| endTime   | query | integer | No  | End Time |
| page      | query | integer | No  | 页码   |
| size      | query | integer | No  | page size  |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/order/trade-list?orderId&symbol&startTime&endTime&page&size' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725512990907' \
--header 'validate-signature: 8f7fcd7be1e099064054a9df8737b2cc0bd410f03cbc4010210db5ab522792b9' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": {
    "page": 1,
    "ps": 10,
    "total": 1,
    "items": [
      {
        "orderId": "401857870576399680",
        "execId": "401857870741635137",
        "symbol": "btc_usdt",
        "quantity": "1977",
        "price": "57170",
        "fee": "6.7815054",
        "feeCoin": "usdt",
        "timestamp": 1725512382543,
        "takerMaker": "TAKER",
        "tradeFeeDetailVO": {
          "orderId": null,
          "execId": null,
          "fee": "6.7815054",
          "couponFee": "0",
          "bonusFee": "6.7815054",
          "realFee": "13.5630108",
          "timestamp": null
        }
      }
    ]
  },
  "ts": 1725512991215
}
```

