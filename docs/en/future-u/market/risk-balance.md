# Get Trading Pair Risk Fund Balance

`GET` /v1/future-u/market/public/contract/risk-balance

## Request Parameters

| name      | location  | type    | required | Description                             |
| --------- | ----- | ------- | ---- | -------------------------------- |
| symbol    | query | string  | Yes   | symbol                           |
| id        | query | integer | No   | id                               |
| direction | query | string  | No   | Direction (PREV: previous page; NEXT: Next page) |
| limit     | query | integer | No   | Page Limit                             |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/contract/risk-balance?symbol=btc_usdt&id&direction&limit' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725509166953' \
--header 'validate-signature: 65cfed6188ac485c728e237da559a28c28c1bca1910df9b108890805db14a872' \
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
        "hasPrev": false,
        "hasNext": true,
        "items": [
            {
                "id": "401654680628789504",
                "coin": "usdt",
                "amount": "11022.7129",
                "createdTime": 1725463938245
            },
            {
                "id": "401272908548178176",
                "coin": "usdt",
                "amount": "11017.0455",
                "createdTime": 1725372916688
            },
            {
                "id": "401265847617749248",
                "coin": "usdt",
                "amount": "11006.5571",
                "createdTime": 1725371233231
            },
            {
                "id": "400914543800254720",
                "coin": "usdt",
                "amount": "11004.0425",
                "createdTime": 1725287475874
            },
            {
                "id": "400901557949858048",
                "coin": "usdt",
                "amount": "10998.9864",
                "createdTime": 1725284379806
            },
            {
                "id": "400821286579765504",
                "coin": "usdt",
                "amount": "10998.8476",
                "createdTime": 1725265241620
            },
            {
                "id": "400821076902314240",
                "coin": "usdt",
                "amount": "10998.1332",
                "createdTime": 1725265191629
            },
            {
                "id": "400820908756861184",
                "coin": "usdt",
                "amount": "10997.9975",
                "createdTime": 1725265151540
            },
            {
                "id": "400820782671888640",
                "coin": "usdt",
                "amount": "10996.9185",
                "createdTime": 1725265121479
            },
            {
                "id": "400817906067210496",
                "coin": "usdt",
                "amount": "10995.8371",
                "createdTime": 1725264435643
            }
        ]
    },
    "ts": 1725509167748
}
```

