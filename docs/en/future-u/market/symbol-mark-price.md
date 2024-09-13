# Get Mark Price for Single Trading Pair

`GET` /v1/future-u/market/public/q/symbol-mark-price

## Request Parameters

| name   | location  | type   | required | Description   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | 否   | symbol |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/q/symbol-mark-price?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725625422516' \
--header 'validate-signature: e9ef9af71450665401daaab96634e908f265c384c1f881ab7c8994221bacbb93' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive'
```

## Response result

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": {
        "s": "btc_usdt",
        "p": "55923.21",
        "t": 1725625421975
    },
    "ts": 1725625422831
}
```

