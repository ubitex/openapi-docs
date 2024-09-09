# 修改止盈止损

`POST` /trade/v2/entrust/update-profit-stop

## 请求参数

| 名称                      | 位置 | 类型         | 必选  | 说明                                        |
| ------------------------- | ---- | ------------ | ----- | ------------------------------------------- |
| profitId                  | body | integer | true  | 止盈止损id                                        |
| triggerProfitPrice        | body | number  | false | 止盈触发价                                        |
| triggerStopPrice          | body | number  | false | 止损触发价                                        |
| triggerPriceType          | body | string  | false | 触发价格类型：INDEX_PRICE(指数价格); MARK_PRICE(标记价格)；LATEST_PRICE(最新价格)                                        |
> 请求示例

```shell

```

## 响应结果

```json

```

