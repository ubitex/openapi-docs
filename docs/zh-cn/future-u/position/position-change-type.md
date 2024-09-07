修改持仓模式

`POST` /v1/future-u/trade/position/v2/change-type

## 请求参数

| 名称           | 位置   | 类型          | 必选   | 说明                            |
|--------------|------|-------------|------|-------------------------------|
| symbol       | body | string | true | 交易对                           |
| positionSide | body | string | true | 仓位方向:LONG(多仓);SHORT(空仓)       |
| positionType | body | string | true | 仓位类型:CROSSED(全仓);ISOLATED(逐仓) |

> 请求示例

```shell

```

## 响应结果

```json

```

