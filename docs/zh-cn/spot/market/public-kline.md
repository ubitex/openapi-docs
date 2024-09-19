# 获取k线数据

`GET` /v1/spot/public/kline

## 请求参数

| 名称      | 位置  | 类型    | 必选 | 说明                                                     |
| --------- | ----- | ------- | ---- | -------------------------------------------------------- |
| symbol    | query | string  | 否   | 交易对                                                   |
| interval  | query | string  | 否   | K线类型[1m;3m;5m;15m;30m;1h;2h;4h;6h;8h;12h;1d;3d;1w;1M] |
| startTime | query | integer | 否   | 开始时间                                                 |
| endTime   | query | integer | 否   | 结束时间                                                 |
| limit     | query | integer | 否   | 限制数量                                                 |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/kline?symbol=btc_usdt&interval=1m&startTime&endTime&limit=5' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521343735' \
--header 'validate-signature: a4d7a2295a501ddd79f9f4f17731b7429bf633ce6a60eb0d4e6312b3826c5d08' \
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
            "t": 1725523140000,
            "o": "57168.00",
            "c": "57168.00",
            "h": "57168.00",
            "l": "57168.00",
            "q": "0.004670",
            "v": "266.97456"
        },
        {
            "t": 1725523080000,
            "o": "57154.00",
            "c": "57167.99",
            "h": "57167.99",
            "l": "57154.00",
            "q": "0.028220",
            "v": "1613.160084"
        },
        {
            "t": 1725523020000,
            "o": "57166.15",
            "c": "57163.63",
            "h": "57166.15",
            "l": "57163.63",
            "q": "0.008180",
            "v": "467.6027018"
        },
        {
            "t": 1725522960000,
            "o": "57161.11",
            "c": "57154.55",
            "h": "57161.11",
            "l": "57154.55",
            "q": "0.070750",
            "v": "4043.6943181"
        },
        {
            "t": 1725522840000,
            "o": "57166.01",
            "c": "57163.97",
            "h": "57166.01",
            "l": "57163.97",
            "q": "0.006580",
            "v": "376.1425946"
        }
    ],
    "ts": 1725523190658
}
```

