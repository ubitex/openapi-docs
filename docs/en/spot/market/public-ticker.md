# Full ticker

`GET` /v1/spot/public/ticker

## Request Parameters

| name    | location  | type          | required | Description                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | No   | symbol                       |
| symbols | query | array[string] | No   | symbol集合，不传时，返回全量 |
| tags    | query | string        | No   | 标签集合                     |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/ticker?symbol=btc_usdt&symbols=&tags' \
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
            "t": 1725523357368,
            "cv": "464.91",
            "cr": "0.0081",
            "o": "56751.10",
            "l": "56194.01",
            "h": "58518.00",
            "c": "57216.01",
            "q": "127.269512",
            "v": "7302614.28610767",
            "ap": "57290.42",
            "aq": "0.210830",
            "bp": "57196.00",
            "bq": "0.046160"
        }
    ],
    "ts": 1725523364762
}
```

