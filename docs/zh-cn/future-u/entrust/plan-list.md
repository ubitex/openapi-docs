# 查询计划委托

`GET` /v1/future-u/trade/entrust/plan-list

## 请求参数

| 名称        | 位置    | 类型      | 必选 | 说明                                                                                                                                                  |
|-----------|-------|---------|----|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | 否  | 交易对                                                                                                                                                 |
| page      | query | integer | 否  | 页码                                                                                                                                                  |
| size      | query | integer | 否  | page size                                                                                                                                                 |
| startTime | query | integer | 否  | 起始时间                                                                                                                                                |
| endTime   | query | integer | 否  | 结束时间                                                                                                                                                |
| state     | query | string  | 否  | 委托状态 NOT_TRIGGERED：新建委托（未触发）；TRIGGERING：触发中；TRIGGERED：已触发；USER_REVOCATION：用户撤销；PLATFORM_REVOCATION：平台撤销（拒绝）；EXPIRED：已过期；UNFINISHED：未完成；HISTORY：（历史） |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/entrust/plan-list?page=1&size=10&symbol=btc_usdt&startTime&endTime&state' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725513605241' \
--header 'validate-signature: 2525119ba9e623cb5a1e7d909e424d915bbee998114cf567480986bec644c789' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## 响应结果

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
            }
        ]
    },
    "ts": 1725513605454
}
```

