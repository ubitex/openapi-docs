`GET` /v1/spot/public/ticker/book

## 请求参数

| 名称    | 位置  | 类型          | 必选 | 说明                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | 否   | 交易对                       |
| symbols | query | array[string] | 否   | 交易对集合，不传时，返回全量 |
| tags    | query | string        | 否   | 标签集合                     |

### 请求示例

/v1/spot/public/ticker/book?symbol=btc_usdt&symbols=&tags


## 响应结果

### 响应示例

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": [
    {
      "s": "btc_usdt",
      "t": 1725521484151,
      "p": "57194.00"
    }
  ],
  "ts": 1725521505786
}
```

