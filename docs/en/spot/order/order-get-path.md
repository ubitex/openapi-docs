# Get single

`GET` /v1/spot/order/{orderId}


## Request Parameters

| name      | location    | type     | required | Description   |
|---------|-------|--------|----|------|
| orderId | path  | string | Yes  | 订单ID |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/order/401878710881651008' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725528998445' \
--header 'validate-signature: 0f60e7af05cb9ae2bde7badfe6cdb1f7db3f9fff92b9e8670f86c59443e7c16d' \
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
    "symbol": "btc_usdt",
    "orderId": "401878710881651008",
    "clientOrderId": "16559590087220001",
    "baseCurrency": "btc",
    "quoteCurrency": "usdt",
    "side": "BUY",
    "type": "LIMIT",
    "timeInForce": "GTC",
    "price": "40000.00",
    "origQty": "2.000000",
    "origQuoteQty": "80000.00",
    "executedQty": "0.000000",
    "leavingQty": "0.000000",
    "tradeBase": "0.000000",
    "tradeQuote": "0.00",
    "avgPrice": null,
    "fee": null,
    "feeCurrency": null,
    "closed": true,
    "state": "CANCELED",
    "time": 1725517351219,
    "updatedTime": 1725522979707
  },
  "ts": 1725541555570
}
```

