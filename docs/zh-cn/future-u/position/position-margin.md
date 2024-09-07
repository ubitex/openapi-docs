修改保证金

`POST` /v1/future-u/trade/position/v2/margin

## 请求参数

| 名称           | 位置   | 类型     | 必选   | 说明                            |
|--------------|------|--------|------|-------------------------------|
| symbol       | body | string | true | 交易对                           |
| positionSide | body | string | true | 持仓方向：LONG;SHORT               |
| margin       | body | number | true | 数量                            |
| type         | body | string | true | 调整方向（ADD：增加逐仓保证金；SUB：减少逐仓保证金） |

> 请求示例

```shell

```

## 响应结果

```json

```

