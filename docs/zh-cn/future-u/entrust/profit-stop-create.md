创建止盈止损

`POST` /trade/v2/entrust/create-profit

## 请求参数

| 名称                        | 位置   | 类型      | 必选    | 说明                                                            |
|---------------------------|------|---------|-------|---------------------------------------------------------------|
| symbol                    | body | string  | true  | 交易对                                                           |
| triggerPriceType          | body | string  | false | 触发价格类型：INDEX_PRICE(指数价格); MARK_PRICE(标记价格)；LATEST_PRICE(最新价格) |
| triggerProfitPrice        | body | number  | false | 止盈触发价                                                         |
| triggerStopPrice          | body | number  | false | 止损触发价                                                         |
| profitDelegateOrderType   | body | string  | false | 订单类型：LIMIT 限价；MARKET 市价                                       |
| profitDelegateTimeInForce | body | string  | false | 止盈委托有效方式：1 GTC、2 FOK、3 IOC 4 GTX                              |
| profitDelegatePrice       | body | number  | false | 止盈委托委托价格                                                      |
| stopDelegateOrderType     | body | string  | false | 止损委托订单类型:1限价、2市价                                              |
| stopDelegateTimeInForce   | body | string  | false | 止损委托有效方式：1 GTC、2 FOK、3 IOC 4 GTX                              |
| stopDelegatePrice         | body | number  | false | 止损委托价格                                                        |
| closeType                 | body | string  | false | 平仓类型:FIXED 固定 ALL 全部                                          |
| origQty                   | body | number  | false | 数量（张）                                                         |
| positionSide              | body | string  | true  | 持仓方向：LONG;SHORT                                               |
| trackNo                   | body | integer | false | trackNo: 交易员带单特有单号，订单有则传                                      |
| clientOrderId             | body | string  | false | 客户端ID                                                         |
| clientMedia               | body | string  | false | 客户端媒体                                                         |
| clientMediaChannel        | body | string  | false | 客户端媒体渠道                                                       |
| expireTime                | body | integer | false | 过期时间                                                          |

> 请求示例

```shell

```

## 响应结果

```json

```

