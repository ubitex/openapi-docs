# Get Ask Bid Market Information for Specific Trading Pair

`GET` /v1/future-u/market/public/q/ticker/book

## Request Parameters

| name   | location  | type   | required | Description   |
| ------ | ----- | ------ | ---- | ------ |
| symbol | query | string | Yes   | symbol |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/q/ticker/book?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725508989122' \
--header 'validate-signature: 9189cbb7f2a8bb2bc6fce8ce67aafcb704bec6568d57c25251a597bf415b9d09' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
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

