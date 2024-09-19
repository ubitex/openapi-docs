# 创建计划委托

`DELETE` /v1/future-u/trade/v2/entrust/create-plan

## 请求参数

| 名称                 | 位置   | 类型      | 必选    | 说明                                                                                                           |
|--------------------|------|---------|-------|--------------------------------------------------------------------------------------------------------------|
| symbol             | body | string  | true  | 交易对                                                                                                          |
| price              | body | number  | false | 价格                                                                                                           |
| stopPrice          | body | number  | false | 触发价                                                                                                          |
| origQty            | body | number  | true  | 数量（张）                                                                                                        |
| entrustType        | body | string  | true  | 委托类型：TAKE_PROFIT(止盈限价单)；STOP(止损限价单)；TAKE_PROFIT_MARKET（止盈市价单）；STOP_MARKET（止损市价单）；TRAILING_STOP_MARKET（跟踪止损单） |
| orderSide          | body | string  | true  | 订单方向：BUY;SELL                                                                                                |
| positionSide       | body | string  | true  | 持仓方向：LONG;SHORT                                                                                              |
| timeInForce        | body | string  | true  | 有效方式：GTC;IOC;FOK;GTX                                                                                         |
| triggerPriceType   | body | string  | true  | 触发价格类型：INDEX_PRICE(指数价格); MARK_PRICE(标记价格)；LATEST_PRICE(最新价格)                                                |
| expireTime         | body | integer | false | 过期时间                                                                                                         |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/v2/entrust/create-plan' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725868395983' \
--header 'validate-signature: d9de65444728d6c04a95979f64b284612770f264bfe6d195996fb64180a866ea' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"symbol":"btc_usdt","price":"50000","stopPrice":"51000","orderSide":"BUY","entrustType":"TAKE_PROFIT","origQty":10,"positionSide":"LONG","timeInForce":"GTC","triggerPriceType":"INDEX_PRICE"}'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": "403351102615109824",
    "ts": 1725868396809
}
```

