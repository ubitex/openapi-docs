# Get Funding Rate Records

`GET` /v1/future-u/market/public/q/funding-rate-record

## Request Parameters

| name      | location  | type    | required | Description                             |
| --------- | ----- | ------- | ---- | -------------------------------- |
| symbol    | query | string  | Yes   | symbol                           |
| id        | query | integer | No   | id                               |
| direction | query | string  | No   | Direction (PREV: previous page; NEXT: Next page) |
| limit     | query | integer | No   | Page Limit                             |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/funding-rate-record?symbol=btc_usdt&id&direction&limit' \
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
        "hasPrev": false,
        "hasNext": true,
        "items": [
            {
                "id": "401842844477766656",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000244",
                "createdTime": 1725508800000,
                "collectionInternal": 3600
            },
            {
                "id": "401827746887580672",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000146",
                "createdTime": 1725505200000,
                "collectionInternal": 3600
            },
            {
                "id": "401812645493160960",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000201",
                "createdTime": 1725501600000,
                "collectionInternal": 3600
            },
            {
                "id": "401797545990372352",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000191",
                "createdTime": 1725498000000,
                "collectionInternal": 3600
            },
            {
                "id": "401782468549622784",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000248",
                "createdTime": 1725494400000,
                "collectionInternal": 3600
            },
            {
                "id": "401767347009960960",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000234",
                "createdTime": 1725490800000,
                "collectionInternal": 3600
            },
            {
                "id": "401752247502978048",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000198",
                "createdTime": 1725487200000,
                "collectionInternal": 3600
            },
            {
                "id": "401737148016966656",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000222",
                "createdTime": 1725483600000,
                "collectionInternal": 3600
            },
            {
                "id": "401722048514178048",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000153",
                "createdTime": 1725480000000,
                "collectionInternal": 3600
            },
            {
                "id": "401706949032360960",
                "symbol": "btc_usdt",
                "fundingRate": "-0.000129",
                "createdTime": 1725476400000,
                "collectionInternal": 3600
            }
        ]
    },
    "ts": 1725509057530
}
```

