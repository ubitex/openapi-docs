# Get Index Price for All Trading Pairs

`GET` /v1/future-u/market/public/q/index-price

## Request Parameters

| name   | location  | type   | required | Description   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | No   | symbol |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/index-price' \
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
      "p": "56.9245",
      "t": 1725625570476
    },
    {
      "s": "xrp_usdt",
      "p": "0.5387",
      "t": 1725625570472
    },
    {
      "s": "vsys_usdt",
      "p": "0.0004",
      "t": 1720244337106
    },
    {
      "s": "trx_usdt",
      "p": "0.14983",
      "t": 1725625570479
    },
    {
      "s": "eth_usdt",
      "p": "2376.85",
      "t": 1725625570465
    },
    {
      "s": "sol_usdt",
      "p": "130.347",
      "t": 1725625570469
    },
    {
      "s": "bnb_usdt",
      "p": "503.41",
      "t": 1725625570474
    },
    {
      "s": "ordi_usdt",
      "p": "28.96",
      "t": 1725625570477
    },
    {
      "s": "btc_usdt",
      "p": "56016.75",
      "t": 1725625570463
    },
    {
      "s": "doge_usdt",
      "p": "0.096488",
      "t": 1725625570467
    },
    {
      "s": "1000shib_usdt",
      "p": "0.013231",
      "t": 1725625570470
    }
  ],
  "ts": 1725625570709
}
```

