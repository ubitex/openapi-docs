# 获取交易对开仓量

`GET` /v1/future-u/market/public/contract/open-interest

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明 |
| ------ | ----- | ------ | ---- | ---- |
| symbol | query | string | 是   | none |

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/contract/open-interest?symbol=btc_usdt' \
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
        "openInterest": "320.9913",
        "openInterestUsd": "19873288.190327",
        "time": 1725509227555
    },
    "ts": 1725509227555
}
```

