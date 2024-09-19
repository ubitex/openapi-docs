# Get Mark Price for Single Trading Pair

`GET` /v1/future-u/market/public/q/symbol-mark-price

## Request Parameters

| name   | location  | type   | required | Description   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | No   | symbol |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/symbol-mark-price?symbol=btc_usdt' \
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
        "s": "btc_usdt",
        "p": "55923.21",
        "t": 1725625421975
    },
    "ts": 1725625422831
}
```

