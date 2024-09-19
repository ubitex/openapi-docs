# 获取全交易对的买一卖一行情信息

`GET` /v1/future-u/market/public/q/ticker/books

## 请求参数

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/ticker/books' \
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
        {
            "s": "trb_usdt",
            "t": 1721494477587,
            "ap": "101",
            "aq": "66",
            "bp": "97.3054",
            "bq": "69"
        },
        {
            "s": "eth_usdt",
            "t": 1725509016642,
            "ap": "2404.98",
            "aq": "350",
            "bp": "2404.94",
            "bq": "326"
        },
        {
            "s": "btc_usdt",
            "t": 1725509016642,
            "ap": "57097.9",
            "aq": "12679",
            "bp": "57097.8",
            "bq": "636"
        },
        {
            "s": "sol_usdt",
            "t": 1725509015643,
            "ap": "131.425",
            "aq": "1190",
            "bp": "131.424",
            "bq": "85"
        },
        {
            "s": "doge_usdt",
            "t": 1721494488597,
            "ap": "0.108",
            "aq": "109325",
            "bp": "0.1076",
            "bq": "31"
        },
        {
            "s": "ordi_usdt",
            "t": 1721494477588,
            "ap": "31.53",
            "aq": "1",
            "bp": "28.52",
            "bq": "1"
        },
        {
            "s": "bnb_usdt",
            "t": 1723800486231,
            "ap": "567.71",
            "aq": "1902",
            "bp": "567.69",
            "bq": "1348"
        },
        {
            "s": "1000shib_usdt",
            "t": 1723793625584,
            "ap": "0.016323",
            "aq": "43",
            "bp": "0.016322",
            "bq": "189"
        },
        {
            "s": "trx_usdt",
            "t": 1723800486241,
            "ap": "0.13563",
            "aq": "1553",
            "bp": "0.13562",
            "bq": "556"
        },
        {
            "s": "xrp_usdt",
            "t": 1723793625584,
            "ap": "0.6137",
            "aq": "25759",
            "bp": "0.6135",
            "bq": "27314"
        }
    ],
    "ts": 1725509018115
}
```

