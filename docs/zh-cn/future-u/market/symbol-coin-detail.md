# 获取币种详情

`GET` /v1/future-u/market/public/symbol/coin/detail

## 请求参数

| 名称   | 位置    | 类型     | 必选 | 说明          |
|------|-------|--------|----|-------------|
| coin | query | string | 否  | 币种，多个币种用,隔开 |

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/coin/detail?coin=btc' \
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
      "coin": "btc",
      "actualPrecision": 8,
      "displayPrecision": 4
    }
  ],
  "ts": 1725623213568
}
```

