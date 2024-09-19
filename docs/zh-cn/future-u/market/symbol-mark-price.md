# 获取单个交易对的标记价格

`GET` /v1/future-u/market/public/q/symbol-mark-price

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | 否   | 交易对 |

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/symbol-mark-price?symbol=btc_usdt' \
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
        "s": "btc_usdt",
        "p": "55923.21",
        "t": 1725625421975
    },
    "ts": 1725625422831
}
```

