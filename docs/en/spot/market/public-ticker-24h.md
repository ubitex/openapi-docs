# Get 24h statistics ticker

`GET` /v1/spot/public/ticker/24h

## Request Parameters

| name    | location  | type          | required | Description                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | No   | symbol                       |
| symbols | query | array[string] | No   | symbol集合，不传时，返回全量 |
| tags    | query | string        | No   | 标签集合                     |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/ticker/24h?symbol=btc_usdt&symbols=&tags' \
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
  "data": [
    {
      "s": "btc_usdt",
      "t": 1725521562400,
      "cv": "663.99",
      "cr": "0.0117",
      "o": "56557.01",
      "l": "56194.01",
      "h": "58518.00",
      "c": "57221.00",
      "q": "144.618422",
      "v": "8283891.33315487"
    }
  ],
  "ts": 1725521583327
}
```

