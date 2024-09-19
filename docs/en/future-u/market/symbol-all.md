# Get all trading pairs

`GET` /v1/future-u/market/public/symbol/all

## Request Parameters

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/all' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725508028956' \
--header 'validate-signature: 33aa7db9c4e38f9c8ec563459d245818f9233e689a84c816cf6d091ccb2fdd81' \
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

