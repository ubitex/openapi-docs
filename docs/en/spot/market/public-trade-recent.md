# Query the list of recent transactions

`GET` /v1/spot/public/trade/recent



## Request Parameters

| name   | location  | type    | required | Description   |
| ------ | ----- | ------- | ---- | ------ |
| symbol | query | string  | No   | symbol |
| limit  | query | integer | No   | 数量   |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/trade/recent?symbol=btc_usdt&limit=2' \
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
            "i": 401904467641141568,
            "t": 1725523492113,
            "p": "57224.00",
            "q": "0.002530",
            "v": "144.77672",
            "b": false
        },
        {
            "i": 401904447382653248,
            "t": 1725523487302,
            "p": "57217.56",
            "q": "0.002220",
            "v": "127.0229832",
            "b": false
        }
    ],
    "ts": 1725523500310
}
```

