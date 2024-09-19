# Close All

`POST` /v1/future-u/trade/position/close-all

## Request Parameters


| name     | location    | type     | required | Description  |
|--------|-------|--------|----|-----|
| symbol | query | string | No  | symbol |

> Request Example

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/position/close-all?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725515043006' \
--header 'validate-signature: 2ea7e8389ecef1edd3506dfed2c0912a4a408bbd7efcdb4d89765d378b42b139' \
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
    "data": true,
    "ts": 1725515043357
}
```

