# Query Stop Limit History

`GET` /v1/future-u/trade/entrust/profit-list-history

## Request Parameters

| name        | location    | type      | required | Description                                                                                                                                                                  |
|-----------|-------|---------|----|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | No  | symbol                                                                                                                                                                 |
| id        | query | integer | No  | id                                                                                                                                                                  |
| direction | query | string  | No  | Direction (PREV: previous page; NEXT: Next page)                                                                                                                                               |
| limit     | query | integer | No  | Page Limit                                                                                                                                                                  |
| startTime | query | integer | No  | Start Time                                                                                                                                                                |
| endTime   | query | integer | No  | End Time                                                                                                                                                                |
| state     | query | string  | No  | 订单状态 NOT_ACTIVATION: 未激活；NOT_TRIGGERED：新建委托（未触发）；TRIGGERING：触发中；TRIGGERED：已触发；USER_REVOCATION：用户撤销；PLATFORM_REVOCATION：平台撤销（拒绝）；EXPIRED：已过期;DELEGATION_FAILED: 委托失败 |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/entrust/profit-list-history?symbol=btc_usdt&id=&direction=NEXT&limit=10&startTime&endTime&state' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725875409618' \
--header 'validate-signature: 08e89691f55b5b5d78c5183627675999dccccbd4a879a068453b03673aec9097' \
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
        "hasPrev": false,
        "hasNext": false,
        "items": [
            {
                "profitId": "403374944700068928",
                "symbol": "btc_usdt",
                "positionSide": "LONG",
                "origQty": "1",
                "triggerPriceType": "INDEX_PRICE",
                "triggerProfitPrice": "56300",
                "triggerStopPrice": "52000",
                "entryPrice": null,
                "positionSize": null,
                "isolatedMargin": null,
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
                "state": "USER_REVOCATION",
                "desc": "user_revocation",
                "triggerPriceSide": "PROFIT",
                "createdTime": 1725874081207,
                "updatedTime": 1725874886660
            }
        ]
    },
    "ts": 1725875409862
}
```

