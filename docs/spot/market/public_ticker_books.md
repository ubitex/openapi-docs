获取最优挂单ticker

`GET` /v1/spot/public/ticker/book

## 请求参数

| 名称    | 位置  | 类型          | 必选 | 说明                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | 否   | 交易对                       |
| symbols | query | array[string] | 否   | 交易对集合，不传时，返回全量 |
| tags    | query | string        | 否   | 标签集合                     |

> 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/spot/public/ticker/book?symbol=btc_usdt&symbols=&tags' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521549434' \
--header 'validate-signature: 863da2ba9d0b0e22a6e2b372a1484b2b12fa47f132b245ea79e3d714a691e148' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' 
```


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

