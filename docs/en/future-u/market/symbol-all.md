# Get all trading pairs

`GET` /v1/future-u/market/public/symbol/all

## Request Parameters

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/all' \
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
        "btc_usdt",
        "eth_usdt",
        "sol_usdt",
        "xrp_usdt",
        "bnb_usdt",
        "trb_usdt",
        "ordi_usdt",
        "true_usdt",
        "trx_usdt",
        "vsys_usdt",
        "doge_usdt",
        "1000shib_usdt"
    ],
    "ts": 1725508029359
}
```

