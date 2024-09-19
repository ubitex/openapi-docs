# Get Latest Transaction Information of Trading Pairs

`GET` /v1/future-u/market/public/q/deal

## Request Parameters

| name     | location    | type      | required | Description  |
|--------|-------|---------|----|-----|
| symbol | query | string  | Yes  | symbol |
| num    | query | integer | Yes  | 数量  |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/deal?symbol=btc_usdt&num=2' \
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
      "t": 1725508398272,
      "s": "btc_usdt",
      "p": "57072.45",
      "a": "165",
      "m": "BID"
    },
    {
      "t": 1725508397292,
      "s": "btc_usdt",
      "p": "57072.45",
      "a": "3200",
      "m": "BID"
    }
  ],
  "ts": 1725508398955
}
```

