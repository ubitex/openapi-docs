# Get Mark Price for All Trading Pairs

`GET` /v1/future-u/market/public/q/mark-price

## Request Parameters

| name   | location  | type   | required | Description   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | No   | symbol |


Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/mark-price' \
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
            "s": "trb_usdt",
            "p": "56.9279",
            "t": 1725625538729
        },
        {
            "s": "xrp_usdt",
            "p": "0.5387",
            "t": 1725625538725
        },
        {
            "s": "vsys_usdt",
            "p": "0.0005",
            "t": 1720244337106
        },
        {
            "s": "trx_usdt",
            "p": "0.14982",
            "t": 1725625538732
        },
        {
            "s": "eth_usdt",
            "p": "2374.21",
            "t": 1725625538718
        },
        {
            "s": "sol_usdt",
            "p": "130.292",
            "t": 1725625538722
        },
        {
            "s": "bnb_usdt",
            "p": "503.34",
            "t": 1725625538727
        },
        {
            "s": "ordi_usdt",
            "p": "28.99",
            "t": 1725625538730
        },
        {
            "s": "btc_usdt",
            "p": "55996.16",
            "t": 1725625538716
        },
        {
            "s": "doge_usdt",
            "p": "0.11",
            "t": 1725625538720
        },
        {
            "s": "1000shib_usdt",
            "p": "0.013231",
            "t": 1725625538723
        }
    ],
    "ts": 1725625539630
}
```

