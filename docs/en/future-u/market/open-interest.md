# Get the open position of a trading pair

`GET` /v1/future-u/market/public/contract/open-interest

## Request Parameters

| name   | location  | type   | required | Description |
| ------ | ----- | ------ | ---- | ---- |
| symbol | query | string | Yes   | none |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/contract/open-interest?symbol=btc_usdt' \
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
        "openInterest": "320.9913",
        "openInterestUsd": "19873288.190327",
        "time": 1725509227555
    },
    "ts": 1725509227555
}
```

