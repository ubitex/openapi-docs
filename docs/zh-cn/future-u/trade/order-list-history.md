# 查询历史订单

`GET` /v1/future-u/trade/order/list-history

## 请求参数

| 名称          | 位置  | 类型    | 必选 | 说明                                                         |
| ------------- | ----- | ------- | ---- | ------------------------------------------------------------ |
| id            | query | integer | 否   | none                                                         |
| direction     | query | string  | 否   | none                                                         |
| limit         | query | integer | 否   | none                                                         |
| symbol        | query | string  | 否   | 交易对                                                       |
| forceClose    | query | boolean | 否   | 是否强平                                                     |
| startTime     | query | integer | 否   | 起始时间                                                     |
| endTime       | query | integer | 否   | 结束时间                                                     |
| origType      | query | integer | 否   | 条件委托类型 1：限价止盈；2：限价止损；3：市价止盈；4：市价止损' |
| orderSide     | query | integer | 否   | 下单方向: 1买、2卖                                           |
| states        | query | string  | 否   | 订单状态 2: 部分成交 3：全部成交；4：用户撤销；6：已过期' (多选 英文逗号分隔) |
| orderOrigType | query | integer | 否   | 历史订单类型  1：限价委托； 2：市价委托； 3：限价止盈止损； 4：市价止盈止损' |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/order/list-history?id&direction=NEXT&limit=100&symbol&forceClose&startTime&endTime&origType&orderSide&states&orderOrigType' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725513004389' \
--header 'validate-signature: 8b4ef0fca045aac30a771dd818410a32e073977fbd3663483cb0d5fb32574f7a' \
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
        "hasPrev": false,
        "hasNext": false,
        "items": [
            {
                "orderId": "401857870576399680",
                "clientOrderId": null,
                "symbol": "btc_usdt",
                "orderType": "MARKET",
                "orderSide": "BUY",
                "positionSide": "LONG",
                "timeInForce": "IOC",
                "closePosition": false,
                "price": "60036.74",
                "origQty": "1977",
                "avgPrice": "57170",
                "executedQty": "1977",
                "marginFrozen": "600.584733",
                "remark": null,
                "sourceId": null,
                "sourceType": "DEFAULT",
                "forceClose": false,
                "closeProfit": null,
                "closeProfitForBonus": null,
                "state": "FILLED",
                "createdTime": 1725512382503,
                "updatedTime": 1725512382516,
                "welfareAccount": false,
                "triggerPriceType": null,
                "triggerProfitPrice": null,
                "profitDelegateOrderType": null,
                "profitDelegateTimeInForce": null,
                "profitDelegatePrice": null,
                "triggerStopPrice": null,
                "stopDelegateOrderType": null,
                "stopDelegateTimeInForce": null,
                "stopDelegatePrice": null,
                "leverage": 20,
                "profit": false
            },
            {
                "orderId": "401302995278811200",
                "clientOrderId": null,
                "symbol": "btc_usdt",
                "orderType": "LIMIT",
                "orderSide": "BUY",
                "positionSide": "LONG",
                "timeInForce": "GTC",
                "closePosition": false,
                "price": "26972.9",
                "origQty": "4",
                "avgPrice": "0",
                "executedQty": "0",
                "marginFrozen": "0.5459315",
                "remark": null,
                "sourceId": null,
                "sourceType": "DEFAULT",
                "forceClose": false,
                "closeProfit": null,
                "closeProfitForBonus": null,
                "state": "CANCELED",
                "createdTime": 1725380089923,
                "updatedTime": 1725511966321,
                "welfareAccount": false,
                "triggerPriceType": null,
                "triggerProfitPrice": null,
                "profitDelegateOrderType": null,
                "profitDelegateTimeInForce": null,
                "profitDelegatePrice": null,
                "triggerStopPrice": null,
                "stopDelegateOrderType": null,
                "stopDelegateTimeInForce": null,
                "stopDelegatePrice": null,
                "leverage": 20,
                "profit": false
            }
        ]
    },
    "ts": 1725513004693
}
```

