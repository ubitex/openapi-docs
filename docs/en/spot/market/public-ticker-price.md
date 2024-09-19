# Get latest prices ticker

`GET` /v1/spot/public/ticker/price

## Request Parameters

| name    | location  | type          | required | Description                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | No   | symbol                       |
| symbols | query | array[string] | No   | symbol集合，不传时，返回全量 |
| tags    | query | string        | No   | 标签集合                     |


Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/ticker/price?symbol=btc_usdt&symbols=&tags' \
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
      "t": 1725521548395,
      "ap": "57202.51",
      "aq": "0.056850",
      "bp": "57111.57",
      "bq": "0.136780"
    }
  ],
  "ts": 1725521549561
}
```

