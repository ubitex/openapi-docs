# Get the best pending order ticker 

`GET` /v1/spot/public/ticker/book

## Request Parameters

| name    | location  | type          | required | Description                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | No   | symbol                       |
| symbols | query | array[string] | No   | symbol集合，不传时，返回全量 |
| tags    | query | string        | No   | 标签集合                     |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/ticker/book?symbol=btc_usdt&symbols=&tags' \
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
      "t": 1725521484151,
      "p": "57194.00"
    }
  ],
  "ts": 1725521505786
}
```

