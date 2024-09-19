# Cancel Stop Limit

`DELETE` /v1/future-u/trade/v2/entrust/cancel-profit-stop

## Request Parameters

| name     | location  | type    | required | Description       |
| -------- | ----- | ------- | ---- | ---------- |
| profitId | query | integer | Yes   | 止盈止损id |

> Request Example

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/future-u/trade/v2/entrust/cancel-profit-stop?profitId=403374944700068928' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725874886160' \
--header 'validate-signature: 3855beb4bed9bbe9d9a31bfcf2b9dceef4b2ea8311822383f28c1ea06fc999d8' \
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
    "data": "403374944700068928",
    "ts": 1725874886685
}
```

