# Query the list of recent transactions

`GET` /v1/spot/public/trade/recent



## Request Parameters

| name   | location  | type    | required | Description   |
| ------ | ----- | ------- | ---- | ------ |
| symbol | query | string  | 否   | symbol |
| limit  | query | integer | 否   | 数量   |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/spot/public/trade/recent?symbol=btc_usdt&limit=2' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521384599' \
--header 'validate-signature: 36822fe15326882cbe9ee4a7f75ac172bbe75314efe080a8b43c7c7160b4aa90' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' 
```

## Response result

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

