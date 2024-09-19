# Get the deposit address

`GET` /v1/spot/deposit/address

## Request Parameters

| name     | location  | type   | required | Description   |
| -------- | ----- | ------ | ---- | ------ |
| currency | query | string | Yes   | coin   |
| chain    | query | string | Yes   | 充值链 |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/deposit/address?currency=usdt&chain=Tron' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725590468383' \
--header 'validate-signature: 050ab8caec00aaf7b7e4c41eb1ab8054fb73caab981214ed689bfed56485c9e6' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' 
```

## Response Result

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": {
        "address": "TRFHq1kdoiBPXLmwnMRLjhUbXuWbyxA3H6",
        "memo": ""
    },
    "ts": 1725590468575
}
```

