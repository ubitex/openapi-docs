`GET` /v1/spot/public/ticker/price

## 请求参数

| 名称    | 位置  | 类型          | 必选 | 说明                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | 否   | 交易对                       |
| symbols | query | array[string] | 否   | 交易对集合，不传时，返回全量 |
| tags    | query | string        | 否   | 标签集合                     |


### 请求示例

/v1/spot/public/ticker/price?symbol=btc_usdt&symbols=&tags


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
      "t": 1725521548395,
      "ap": "57202.51",
      "aq": "0.056850",
      "bp": "57111.57",
      "bq": "0.136780"
    }
  ],
  "ts": 1725521549561
}
```

