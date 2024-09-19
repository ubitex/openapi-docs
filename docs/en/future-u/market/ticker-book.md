# Get Ask Bid Market Information for Specific Trading Pair

`GET` /v1/future-u/market/public/q/ticker/book

## Request Parameters

| name   | location  | type   | required | Description   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | Yes   | symbol |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/ticker/book?symbol=btc_usdt' \
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
        "t": 1725508988642,
        "ap": "57094.4",
        "aq": "7058",
        "bp": "57094.3",
        "bq": "20541"
    },
    "ts": 1725508989564
}
```

