# Get Configuration Information for Single Trading Pair

`GET` /v1/future-u/market/public/symbol/detail

## Request Parameters

| name     | location    | type     | required | Description     |
|--------|-------|--------|----|--------|
| symbol | query | string | Yes  | symbol |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/detail?symbol=btc_usdt' \
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
        "id": 1,
        "symbol": "btc_usdt",
        "symbolGroupId": 1,
        "pair": "btc_usdt",
        "contractType": "PERPETUAL",
        "productType": "perpetual",
        "predictEventType": null,
        "predictEventParam": null,
        "predictEventSort": null,
        "underlyingType": "U_BASED",
        "contractSize": "0.0001",
        "tradeSwitch": true,
        "openSwitch": true,
        "isDisplay": true,
        "isOpenApi": true,
        "state": 0,
        "initLeverage": 20,
        "initPositionType": "CROSSED",
        "baseCoin": "btc",
        "quoteCoin": "usdt",
        "baseCoinPrecision": 8,
        "baseCoinDisplayPrecision": 4,
        "quoteCoinPrecision": 8,
        "quoteCoinDisplayPrecision": 4,
        "quantityPrecision": 0,
        "pricePrecision": 2,
        "supportOrderType": "LIMIT,MARKET",
        "supportTimeInForce": "GTC,FOK,IOC,GTX",
        "supportEntrustType": "TAKE_PROFIT,STOP,TAKE_PROFIT_MARKET,STOP_MARKET,TRAILING_STOP_MARKET",
        "supportPositionType": "CROSSED,ISOLATED",
        "minQty": "1",
        "minNotional": "10",
        "maxNotional": "10000000000",
        "multiplierDown": "0.5",
        "multiplierUp": "0.5",
        "maxOpenOrders": 20000000,
        "maxEntrusts": 20000000,
        "makerFee": "0.0002",
        "takerFee": "0.00065",
        "liquidationFee": "0.015",
        "marketTakeBound": "0.05",
        "depthPrecisionMerge": 6,
        "labels": [
            "HOT",
            "NEW"
        ],
        "onboardDate": 1651327201000,
        "enName": "BTCUSDT",
        "cnName": "BTCUSDT ",
        "minStepPrice": "0.01",
        "minPrice": null,
        "maxPrice": null,
        "deliveryDate": 1667819989000,
        "deliveryPrice": null,
        "deliveryCompletion": false,
        "cnDesc": "cn",
        "enDesc": "en en",
        "cnRemark": null,
        "enRemark": null,
        "plates": [
            3
        ]
    },
    "ts": 1725623347622
}
```

