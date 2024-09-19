# 获取指定交易对的聚合行情信息

`GET` /v1/future-u/market/public/q/agg-ticker

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | 是   | 交易对 |

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/agg-ticker?symbol=btc_usdt' \
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
        "t": 1725508271643,
        "s": "btc_usdt",
        "c": "57081.05",
        "h": "58498.95",
        "l": "56156.15",
        "a": "529885960",
        "v": "3044068057",
        "o": "57702.70",
        "r": "-0.0107",
        "i": "57105.42",
        "m": "57082.17",
        "bp": "57081.0",
        "ap": "57081.1"
    },
    "ts": 1725508273013
}
```

