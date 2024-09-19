# Get currency information

`GET` /v1/spot/public/currencies

## Request Parameters

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/currencies?accessKey=2fa91add-388c-44f2-8365-f4b72886c135&secretKey=6fb7fc1dde997cc03e75a460d07184c9c9a14704' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725522327919' \
--header 'validate-signature: 6926466add838acacb21492954dc7c098870dba09b0de9a088d811840b158e9b' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": {
    "time": 1725074611203,
    "version": "028a2fd226e3c4b6e857bd0a80b7f255",
    "currencies": [
      {
        "id": 2,
        "currency": "btc",
        "displayName": "BTC",
        "fullName": "Bitcoin",
        "logo": "https://ubit-dev.s3.ap-northeast-1.amazonaws.com/1/currency/微信截图_20240722193458.png",
        "cmcLink": "https://coinmarketcap.com/currencies/bitcoin/",
        "weight": 99999,
        "maxPrecision": 10,
        "depositStatus": 1,
        "withdrawStatus": 1,
        "convertEnabled": 1,
        "transferEnabled": 1,
        "isChainExist": 1,
        "ubcardEnabled": 0,
        "plates": []
      },
      {
        "id": 5,
        "currency": "eth",
        "displayName": "ETH",
        "fullName": "Ethereum",
        "logo": "https://ubit-dev.s3.ap-northeast-1.amazonaws.com/1/currency/微信截图_20240722193458.png",
        "cmcLink": "https://coinmarketcap.com/currencies/ethereum/",
        "weight": 99998,
        "maxPrecision": 8,
        "depositStatus": 1,
        "withdrawStatus": 1,
        "convertEnabled": 1,
        "transferEnabled": 1,
        "isChainExist": 1,
        "ubcardEnabled": 0,
        "plates": []
      },
      {
        "id": 11,
        "currency": "usdt",
        "displayName": "USDT",
        "fullName": "Tether USDt",
        "logo": "https://s2.coinmarketcap.com/static/img/coins/64x64/825.png",
        "cmcLink": "https://coinmarketcap.com/currencies/tether/",
        "weight": 99997,
        "maxPrecision": 8,
        "depositStatus": 1,
        "withdrawStatus": 1,
        "convertEnabled": 1,
        "transferEnabled": 1,
        "isChainExist": 1,
        "ubcardEnabled": 1,
        "plates": []
      },
      {
        "id": 90,
        "currency": "xrp",
        "displayName": "XRP",
        "fullName": "XRP",
        "logo": "https://s2.coinmarketcap.com/static/img/coins/64x64/52.png",
        "cmcLink": "https://coinmarketcap.com/currencies/xrp/",
        "weight": 99996,
        "maxPrecision": 8,
        "depositStatus": 1,
        "withdrawStatus": 1,
        "convertEnabled": 1,
        "transferEnabled": 1,
        "isChainExist": 1,
        "ubcardEnabled": 0,
        "plates": []
      }
    ]
  },
  "ts": 1725522329567
}
```

