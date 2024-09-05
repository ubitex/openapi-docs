`GET` /v1/spot/public/ticker/24h



## 请求参数

| 名称    | 位置  | 类型          | 必选 | 说明                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | 否   | 交易对                       |
| symbols | query | array[string] | 否   | 交易对集合，不传时，返回全量 |
| tags    | query | string        | 否   | 标签集合                     |

### 请求示例

/v1/spot/public/ticker/24h?symbol=btc_usdt&symbols=&tags


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
      "t": 1725521562400,
      "cv": "663.99",
      "cr": "0.0117",
      "o": "56557.01",
      "l": "56194.01",
      "h": "58518.00",
      "c": "57221.00",
      "q": "144.618422",
      "v": "8283891.33315487"
    }
  ],
  "ts": 1725521583327
}
```

