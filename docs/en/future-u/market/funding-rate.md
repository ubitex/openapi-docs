# Get Funding Rate Information

`GET` /v1/future-u/market/public/q/funding-rate

## Request Parameters

| name     | location    | type     | required | Description  |
|--------|-------|--------|----|-----|
| symbol | query | string | Yes  | symbol |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/funding-rate?symbol=btc_usdt' \
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
    "symbol": "btc_usdt",
    "fundingRate": -0.000245,
    "nextCollectionTime": 1725512400000,
    "collectionInternal": 1
  },
  "ts": 1725508951530
}
```

