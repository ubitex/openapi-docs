# 获取指定交易对的买一卖一行情信息

`GET` /v1/future-u/market/public/q/ticker/book

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | 是   | 交易对 |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/ticker/book?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725508989122' \
--header 'validate-signature: 9189cbb7f2a8bb2bc6fce8ce67aafcb704bec6568d57c25251a597bf415b9d09' \
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
        "t": 1725508988642,
        "ap": "57094.4",
        "aq": "7058",
        "bp": "57094.3",
        "bq": "20541"
    },
    "ts": 1725508989564
}
```

