获取交易对币种

`GET` /v1/future-u/market/public/symbol/coins

## 请求参数

### 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/symbol/coins' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725507803626' \
--header 'validate-signature: 04d10e726ace5163331e7fe6d26f3b97b829a712cc7cd8eeed2fc3bb02f28c50' \
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
    "data": [
        "usdt"
    ],
    "ts": 1725507804044
}
```

