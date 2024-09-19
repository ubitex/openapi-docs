# See Leverage Stratification of Single Trading Pair 

`GET` /v1/future-u/market/public/leverage/bracket/detail

## Request Parameters

| name     | location    | type     | required | Description   |
|--------|-------|--------|----|------|
| symbol | query | string | Yes  | none |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/leverage/bracket/detail?symbol=btc_usdt' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

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

