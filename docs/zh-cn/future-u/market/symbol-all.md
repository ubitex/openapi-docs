# 获取所有交易对

`GET` /v1/future-u/market/public/symbol/all

## 请求参数

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/all' \
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
        "btc_usdt",
        "eth_usdt",
        "sol_usdt",
        "xrp_usdt",
        "bnb_usdt",
        "trb_usdt",
        "ordi_usdt",
        "true_usdt",
        "trx_usdt",
        "vsys_usdt",
        "doge_usdt",
        "1000shib_usdt"
    ],
    "ts": 1725508029359
}
```

