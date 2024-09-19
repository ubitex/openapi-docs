# Query Order History

`GET` /v1/future-u/trade/order/list-history

## Request Parameters

| name          | location  | type    | required | Description                                   |
| ------------- | ----- | ------- | ---- |-----------------------------------------------|
| id            | query | integer | No   | none                                          |
| direction     | query | string  | No   | none                                          |
| limit         | query | integer | No   | none                                          |
| symbol        | query | string  | No   | symbol                                        |
| forceClose    | query | boolean | No   | 是否强平                                          |
| startTime     | query | integer | No   | Start Time                                    |
| endTime       | query | integer | No   | End Time                                      |
| origType      | query | integer | No   | 条件委托type 1：限价止盈；2：限价止损；3：市价止盈；4：市价止损'         |
| orderSide     | query | integer | No   | 下单方向: 1买、2卖                                   |
| states        | query | string  | No   | 订单状态 2: 部分成交 3：全部成交；4：用户撤销；6：已过期' (多选 英文逗号分隔) |
| orderOrigType | query | integer | No   | 历史订单type  1：限价委托； 2：市价委托； 3：限价止盈止损； 4：市价止盈止损' |

> Request Example

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

