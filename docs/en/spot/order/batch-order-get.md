# Get batch

`GET` /v1/spot/batch-order

## Request Parameters

| name       | location    | type     | required | Description             |
|----------|-------|--------|----|----------------|
| orderIds | query | string | Yes  | 订单ID集合(最多100条) |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/batch-order?orderIds=401876438755871040,401653869310150976&abc=' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725547256697' \
--header 'validate-signature: 645a9fec92ca103d968c73099a057de277d1a0258284555b70fa813d83189d94' \
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
  "data": [
    {
      "symbol": "btc_usdt",
      "orderId": "401876438755871040",
      "clientOrderId": "16559590087220001",
      "baseCurrency": "btc",
      "quoteCurrency": "usdt",
      "side": "BUY",
      "type": "LIMIT",
      "timeInForce": "GTC",
      "price": "40000.00",
      "origQty": "0.500010",
      "origQuoteQty": "20000.40",
      "executedQty": "0.000000",
      "leavingQty": "0.500010",
      "tradeBase": "0.000000",
      "tradeQuote": "0.00",
      "avgPrice": null,
      "fee": null,
      "feeCurrency": null,
      "closed": false,
      "state": "NEW",
      "time": 1725516809502,
      "updatedTime": 1725516809657
    },
    {
      "symbol": "btc_usdt",
      "orderId": "401653869310150976",
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
      "leavingQty": "2.000000",
      "tradeBase": "0.000000",
      "tradeQuote": "0.00",
      "avgPrice": null,
      "fee": null,
      "feeCurrency": null,
      "closed": false,
      "state": "NEW",
      "time": 1725463744811,
      "updatedTime": 1725463744873
    }
  ],
  "ts": 1725547257538
}
```

