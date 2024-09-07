# 撤销计划委托

`DELETE` /trade/v2/entrust/cancel-plan

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
| marketOrderLevel   | body | integer | false | 市价最优档：1：对手价；当前价；5，10，15挡                                                                                     |
| expireTime         | body | integer | false | 过期时间                                                                                                         |
| clientOrderId      | body | string  | false | 客户端ID                                                                                                        |
| clientMedia        | body | string  | false | 客户端媒体                                                                                                        |
| clientMediaChannel | body | string  | false | 客户端媒体渠道                                                                                                      |

> 请求示例

```shell


```

## 响应结果

```json

```

