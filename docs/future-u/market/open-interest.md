获取交易对开仓量

`GET` /v1/future-u/market/public/contract/open-interest

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明 |
| ------ | ----- | ------ | ---- | ---- |
| symbol | query | string | 是   | none |

### 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/contract/open-interest?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725509227074' \
--header 'validate-signature: bf84be5183f4d1f5ab4ae26a7bfea3e67a0134f22547ec72e855bc729c5d3c2f' \
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
        "symbol": "btc_usdt",
        "openInterest": "320.9913",
        "openInterestUsd": "19873288.190327",
        "time": 1725509227555
    },
    "ts": 1725509227555
}
```

