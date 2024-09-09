# 创建止盈止损

`POST` /trade/v2/entrust/create-profit

## 请求参数

| 名称                        | 位置   | 类型      | 必选    | 说明                                                            |
|---------------------------|------|---------|-------|---------------------------------------------------------------|
| symbol                    | body | string  | true  | 交易对                                                           |
| triggerPriceType          | body | string  | false | 触发价格类型：INDEX_PRICE(指数价格); MARK_PRICE(标记价格)；LATEST_PRICE(最新价格) |
| triggerProfitPrice        | body | number  | false | 止盈触发价                                                         |
| triggerStopPrice          | body | number  | false | 止损触发价                                                         |
| origQty                   | body | number  | false | 数量（张）                                                         |
| positionSide              | body | string  | true  | 持仓方向：LONG;SHORT                                               |
| expireTime                | body | integer | false | 过期时间                                                          |

> 请求示例

```shell

```

## 响应结果

```json

```

