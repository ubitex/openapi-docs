# See Leverage Stratification of All Trading Pairs

`GET` /v1/future-u/market/public/leverage/bracket/list

## Request Parameters

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/leverage/bracket/list' \
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
    "data": [
        {
            "symbol": "trb_usdt",
            "leverageBrackets": [
                {
                    "symbol": "trb_usdt",
                    "bracket": 1,
                    "maxNominalValue": "5000",
                    "maintMarginRate": "0.025",
                    "startMarginRate": "0.05",
                    "maxStartMarginRate": null,
                    "maxLeverage": "10",
                    "minLeverage": "1"
                },
                {
                    "symbol": "trb_usdt",
                    "bracket": 2,
                    "maxNominalValue": "25000",
                    "maintMarginRate": "0.05",
                    "startMarginRate": "0.1",
                    "maxStartMarginRate": null,
                    "maxLeverage": "8",
                    "minLeverage": "1"
                },
                {
                    "symbol": "trb_usdt",
                    "bracket": 3,
                    "maxNominalValue": "250000",
                    "maintMarginRate": "0.1",
                    "startMarginRate": "0.2",
                    "maxStartMarginRate": null,
                    "maxLeverage": "5",
                    "minLeverage": "1"
                },
                {
                    "symbol": "trb_usdt",
                    "bracket": 4,
                    "maxNominalValue": "1000000",
                    "maintMarginRate": "0.125",
                    "startMarginRate": "0.25",
                    "maxStartMarginRate": null,
                    "maxLeverage": "2",
                    "minLeverage": "1"
                },
                {
                    "symbol": "trb_usdt",
                    "bracket": 5,
                    "maxNominalValue": "3000000",
                    "maintMarginRate": "0.5",
                    "startMarginRate": "0.1",
                    "maxStartMarginRate": null,
                    "maxLeverage": "1",
                    "minLeverage": "1"
                }
            ]
        },
        {
            "symbol": "true_usdt",
            "leverageBrackets": [
                {
                    "symbol": "true_usdt",
                    "bracket": 1,
                    "maxNominalValue": "5000",
                    "maintMarginRate": "0.0065",
                    "startMarginRate": "0.013",
                    "maxStartMarginRate": null,
                    "maxLeverage": "75",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 2,
                    "maxNominalValue": "50000",
                    "maintMarginRate": "0.01",
                    "startMarginRate": "0.02",
                    "maxStartMarginRate": null,
                    "maxLeverage": "50",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 3,
                    "maxNominalValue": "500000",
                    "maintMarginRate": "0.025",
                    "startMarginRate": "0.05",
                    "maxStartMarginRate": null,
                    "maxLeverage": "20",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 4,
                    "maxNominalValue": "1200000",
                    "maintMarginRate": "0.05",
                    "startMarginRate": "0.1",
                    "maxStartMarginRate": null,
                    "maxLeverage": "10",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 5,
                    "maxNominalValue": "3000000",
                    "maintMarginRate": "0.1",
                    "startMarginRate": "0.2",
                    "maxStartMarginRate": null,
                    "maxLeverage": "5",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 6,
                    "maxNominalValue": "6000000",
                    "maintMarginRate": "0.13",
                    "startMarginRate": "0.25",
                    "maxStartMarginRate": null,
                    "maxLeverage": "4",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 7,
                    "maxNominalValue": "12000000",
                    "maintMarginRate": "0.15",
                    "startMarginRate": "0.3",
                    "maxStartMarginRate": null,
                    "maxLeverage": "3",
                    "minLeverage": "1"
                },
                {
                    "symbol": "true_usdt",
                    "bracket": 8,
                    "maxNominalValue": "20000000",
                    "maintMarginRate": "0.25",
                    "startMarginRate": "0.5",
                    "maxStartMarginRate": null,
                    "maxLeverage": "2",
                    "minLeverage": "1"
                }
            ]
        }
    ],
    "ts": 1725507968008
}
```

