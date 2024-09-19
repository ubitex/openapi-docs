# 获取资金费率

`GET` /v1/future-u/market/public/q/funding-rate

## 请求参数

| 名称     | 位置    | 类型     | 必选 | 说明  |
|--------|-------|--------|----|-----|
| symbol | query | string | 是  | 交易对 |

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/funding-rate?symbol=btc_usdt' \
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
  "data": {
    "symbol": "btc_usdt",
    "fundingRate": -0.000245,
    "nextCollectionTime": 1725512400000,
    "collectionInternal": 1
  },
  "ts": 1725508951530
}
```

