# Query Stop Limit

`GET` /v1/future-u/trade/entrust/profit-list

## Request Parameters

| name        | location    | type      | required | Description                                                                                                                                                  |
|-----------|-------|---------|----|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | No  | symbol                                                                                                                                                 |
| page      | query | integer | No  | 页码                                                                                                                                                  |
| size      | query | integer | No  | page size                                                                                                                                                 |
| startTime | query | integer | No  | Start Time                                                                                                                                                |
| endTime   | query | integer | No  | End Time                                                                                                                                                |
| state     | query | string  | No  | 委托状态 NOT_TRIGGERED：新建委托（未触发）；TRIGGERING：触发中；TRIGGERED：已触发；USER_REVOCATION：用户撤销；PLATFORM_REVOCATION：平台撤销（拒绝）；EXPIRED：已过期；UNFINISHED：未完成；HISTORY：（历史） |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/entrust/profit-list?symbol=btc_usdt&page=1&size=10&startTime&endTime&state' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725874271866' \
--header 'validate-signature: 6ab89fa414e03238a55c026ed6672213af142065a12845d7c1021aeb70374aaa' \
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
                "profitId": "403374944700068928",
                "symbol": "btc_usdt",
                "positionSide": "LONG",
                "origQty": "1",
                "triggerPriceType": "INDEX_PRICE",
                "triggerProfitPrice": "56300",
                "triggerStopPrice": "52000",
                "entryPrice": "55279.8",
                "positionSize": "10",
                "isolatedMargin": "2.76399",
                "executedQty": "0",
                "avgPrice": null,
                "positionType": "CROSSED",
                "delegateQty": null,
                "delegatePrice": null,
                "profitDelegateOrderType": "MARKET",
                "profitDelegateTimeInForce": "IOC",
                "profitDelegatePrice": null,
                "stopDelegateOrderType": "MARKET",
                "stopDelegateTimeInForce": "IOC",
                "stopDelegatePrice": null,
                "closeType": "FIXED",
                "state": "NOT_TRIGGERED",
                "desc": null,
                "triggerPriceSide": "PROFIT",
                "createdTime": 1725874081207,
                "updatedTime": 1725874081207
            }
        ]
    },
    "ts": 1725874272131
}
```

