# Query historical transaction list

`GET` /v1/spot/public/trade/history

## Request Parameters

| name      | location  | type    | required | Description                             |
| --------- | ----- | ------- | ---- | -------------------------------- |
| symbol    | query | string  | No   | symbol                           |
| direction | query | string  | No   | Direction (PREV: previous page; NEXT: Next page) |
| fromId    | query | integer | No   | 起始ID                           |
| limit     | query | integer | No   | 数量                             |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/trade/history?symbol=btc_usdt&direction=NEXT&fromId&limit=2' \
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
    "data": {
        "hasPrev": false,
        "hasNext": true,
        "items": [
            {
                "i": 401904210568055104,
                "t": 1725523430831,
                "p": "57212.01",
                "q": "0.001450",
                "v": "82.9574145",
                "b": true
            },
            {
                "i": 401904120491182400,
                "t": 1725523409356,
                "p": "57231.10",
                "q": "0.033930",
                "v": "1941.851223",
                "b": true
            }
        ]
    },
    "ts": 1725523439385
}
```

