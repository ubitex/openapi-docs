# 获取交易对的最新成交信息

`GET` /v1/future-u/market/public/q/deal

## 请求参数

| 名称     | 位置    | 类型      | 必选 | 说明  |
|--------|-------|---------|----|-----|
| symbol | query | string  | 是  | 交易对 |
| num    | query | integer | 是  | 数量  |

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/deal?symbol=btc_usdt&num=2' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## 响应结果

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": [
    {
      "t": 1725508398272,
      "s": "btc_usdt",
      "p": "57072.45",
      "a": "165",
      "m": "BID"
    },
    {
      "t": 1725508397292,
      "s": "btc_usdt",
      "p": "57072.45",
      "a": "3200",
      "m": "BID"
    }
  ],
  "ts": 1725508398955
}
```

