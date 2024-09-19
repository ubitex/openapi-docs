# Query Trigger Orders By entrustId

`GET` /v1/future-u/trade/entrust/plan-detail

## Request Parameters

| name      | location  | type    | required | Description |
| --------- | ----- | ------- | ---- | ---- |
| entrustId | query | integer | Yes   | none |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/entrust/plan-detail?entrustId=401862973001741632' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725513623734' \
--header 'validate-signature: c3294b585d91ef946be4c0410a775e8fe7d9617c4c2b5cd7e41e77a778c24c99' \
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
        "entrustId": "401862973001741632",
        "symbol": "btc_usdt",
        "entrustType": "TAKE_PROFIT",
        "orderSide": "BUY",
        "positionSide": "LONG",
        "timeInForce": "GTC",
        "closePosition": null,
        "price": "57115.65",
        "origQty": "1936",
        "stopPrice": "50000",
        "triggerPriceType": "LATEST_PRICE",
        "executedQty": null,
        "avgPrice": null,
        "state": "NOT_TRIGGERED",
        "marketOrderLevel": null,
        "createdTime": 1725513599041,
        "updatedTime": 1725513599041,
        "ordinary": false
    },
    "ts": 1725513623945
}
```

