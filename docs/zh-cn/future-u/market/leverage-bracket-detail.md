# 查询单个交易对杠杆分层

`GET` /v1/future-u/market/public/leverage/bracket/detail

## 请求参数

| 名称     | 位置    | 类型     | 必选 | 说明   |
|--------|-------|--------|----|------|
| symbol | query | string | 是  | none |

> 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/leverage/bracket/detail?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725507938857' \
--header 'validate-signature: c3391bbe1e26c6e1d9294aa244ac8afb5339e1fd3bdcbb4fad3dab9fe05ee749' \
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
    "leverageBrackets": [
      {
        "symbol": "btc_usdt",
        "bracket": 1,
        "maxNominalValue": "50000",
        "maintMarginRate": "0.004",
        "startMarginRate": "0.008",
        "maxStartMarginRate": null,
        "maxLeverage": "125",
        "minLeverage": "1"
      },
      {
        "symbol": "btc_usdt",
        "bracket": 2,
        "maxNominalValue": "100000",
        "maintMarginRate": "0.005",
        "startMarginRate": "0.01",
        "maxStartMarginRate": null,
        "maxLeverage": "100",
        "minLeverage": "1"
      },
      {
        "symbol": "btc_usdt",
        "bracket": 3,
        "maxNominalValue": "200000",
        "maintMarginRate": "0.006",
        "startMarginRate": "0.013",
        "maxStartMarginRate": null,
        "maxLeverage": "75",
        "minLeverage": "1"
      },
      {
        "symbol": "btc_usdt",
        "bracket": 4,
        "maxNominalValue": "400000",
        "maintMarginRate": "0.01",
        "startMarginRate": "0.02",
        "maxStartMarginRate": null,
        "maxLeverage": "50",
        "minLeverage": "1"
      },
      {
        "symbol": "btc_usdt",
        "bracket": 5,
        "maxNominalValue": "500000",
        "maintMarginRate": "0.015",
        "startMarginRate": "0.025",
        "maxStartMarginRate": null,
        "maxLeverage": "40",
        "minLeverage": "1"
      },
      {
        "symbol": "btc_usdt",
        "bracket": 6,
        "maxNominalValue": "10000000",
        "maintMarginRate": "0.03",
        "startMarginRate": "0.05",
        "maxStartMarginRate": null,
        "maxLeverage": "33",
        "minLeverage": "1"
      },
      {
        "symbol": "btc_usdt",
        "bracket": 7,
        "maxNominalValue": "99999999999",
        "maintMarginRate": "0.029",
        "startMarginRate": "0.04",
        "maxStartMarginRate": null,
        "maxLeverage": "25",
        "minLeverage": "1"
      }
    ]
  },
  "ts": 1725507939794
}
```

