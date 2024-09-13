# Get currency details

`GET` /v1/future-u/market/public/symbol/coin/detail

## Request Parameters

| name   | location    | type     | required | Description          |
|------|-------|--------|----|-------------|
| coin | query | string | No  | coin，多个币种用,隔开 |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/symbol/coin/detail?coin=btc' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725623213188' \
--header 'validate-signature: 312de035fa698a91e6337ba16b59d47202c56e67cfd2e52b8c46a06e0086a796' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive'
```

## Response result

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

