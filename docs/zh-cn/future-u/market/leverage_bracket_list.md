查询所有交易对杠杆分层

`GET` /v1/future-u/market/public/leverage/bracket/list

## 请求参数

> 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/leverage/bracket/list' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725507967555' \
--header 'validate-signature: 27f48c1fad34f559450a9b8cf36a5607912afc812a397b6c78697f4a42f82bf2' \
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

