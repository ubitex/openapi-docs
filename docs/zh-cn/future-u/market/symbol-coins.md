# 获取交易对币种

`GET` /v1/future-u/market/public/symbol/coins

## 请求参数

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/coins' \
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
        "usdt"
    ],
    "ts": 1725507804044
}
```

