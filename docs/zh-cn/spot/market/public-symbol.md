# 获取交易对信息

`GET` /v1/spot/public/symbol


## 请求参数

| 名称    | 位置  | 类型          | 必选 | 说明                                                        |
| ------- | ----- | ------------- | ---- | ----------------------------------------------------------- |
| symbol  | query | string        | 否   | 交易对                                                      |
| symbols | query | array[string] | 否   | 交易对集合                                                  |
| version | query | string        | 否   | 版本号,当请求版本号与响应内容版本一致时，不返回清单，减少IO |

> 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/spot/public/symbol?symbol=btc_usdt&symbols=&version&tags' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521245226' \
--header 'validate-signature: 4d09d1d3f75b2a2db923104051c25848e4b161fa631f1baa78e5d81fa2b390f8' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' 
```


## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": {
        "time": 1725523296730,
        "version": "ae0ac0cef0ef3bfde740e013eac9a9e3",
        "symbols": [
            {
                "id": 614,
                "symbol": "btc_usdt",
                "displayName": "BTC_USDT",
                "state": "ONLINE",
                "stateTime": 1721479941000,
                "tradingEnabled": true,
                "openapiEnabled": true,
                "nextStateTime": null,
                "nextState": null,
                "depthMergePrecision": 5,
                "baseCurrency": "btc",
                "baseCurrencyPrecision": 10,
                "baseCurrencyId": 2,
                "quoteCurrency": "usdt",
                "quoteCurrencyPrecision": 8,
                "quoteCurrencyId": 11,
                "pricePrecision": 2,
                "quantityPrecision": 6,
                "orderTypes": [
                    "LIMIT",
                    "MARKET"
                ],
                "timeInForces": [
                    "GTC",
                    "IOC"
                ],
                "displayWeight": 10001,
                "displayLevel": "FULL",
                "plates": [],
                "filters": [
                    {
                        "filter": "QUANTITY",
                        "min": "0.001",
                        "max": "100",
                        "tickSize": "0.00001"
                    },
                    {
                        "filter": "QUOTE_QTY",
                        "min": "5"
                    },
                    {
                        "filter": "PROTECTION_LIMIT",
                        "buyMaxDeviation": "0.8",
                        "sellMaxDeviation": "0.8"
                    },
                    {
                        "filter": "PROTECTION_MARKET",
                        "maxDeviation": "0.1"
                    }
                ]
            }
        ]
    },
    "ts": 1725523296730
}
```

