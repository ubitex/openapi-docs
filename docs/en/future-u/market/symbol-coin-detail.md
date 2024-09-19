# Get currency details

`GET` /v1/future-u/market/public/symbol/coin/detail

## Request Parameters

| name   | location    | type     | required | Description          |
|------|-------|--------|----|-------------|
| coin | query | string | No  | coin，多个币种用,隔开 |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/symbol/coin/detail?coin=btc' \
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
      "coin": "btc",
      "actualPrecision": 8,
      "displayPrecision": 4
    }
  ],
  "ts": 1725623213568
}
```

