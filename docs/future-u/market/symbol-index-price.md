获取单个交易对的指数价格

`GET` /v1/future-u/market/public/q/symbol-index-price

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | 否   | 交易对 |

### 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/q/symbol-index-price?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725624638072' \
--header 'validate-signature: ba2b0e3112ce9f89a9f9d383a7b74cd154ed27ae1629c56a5ac2004e17264fe7' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
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
        "p": "55907.84",
        "t": 1725624637534
    },
    "ts": 1725624638502
}
```

