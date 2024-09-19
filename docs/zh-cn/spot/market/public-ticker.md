# 完整ticker

`GET` /v1/spot/public/ticker

## 请求参数

| 名称    | 位置  | 类型          | 必选 | 说明                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | 否   | 交易对                       |
| symbols | query | array[string] | 否   | 交易对集合，不传时，返回全量 |
| tags    | query | string        | 否   | 标签集合                     |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/ticker?symbol=btc_usdt&symbols=&tags' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521471887' \
--header 'validate-signature: c2275ac44ce3b1090a6d689adb1ec574223e394a40a3f1c0b68c440edfb3c8ef' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' 
```


## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": [
        {
            "s": "btc_usdt",
            "t": 1725523357368,
            "cv": "464.91",
            "cr": "0.0081",
            "o": "56751.10",
            "l": "56194.01",
            "h": "58518.00",
            "c": "57216.01",
            "q": "127.269512",
            "v": "7302614.28610767",
            "ap": "57290.42",
            "aq": "0.210830",
            "bp": "57196.00",
            "bq": "0.046160"
        }
    ],
    "ts": 1725523364762
}
```

