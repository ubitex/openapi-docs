# Get latest prices ticker

`GET` /v1/spot/public/ticker/price

## Request Parameters

| name    | location  | type          | required | Description                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | 否   | symbol                       |
| symbols | query | array[string] | 否   | symbol集合，不传时，返回全量 |
| tags    | query | string        | 否   | 标签集合                     |


> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/spot/public/ticker/price?symbol=btc_usdt&symbols=&tags' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521505660' \
--header 'validate-signature: f9904984c07e2758858dc4f2b902d199ed170cce10d2b74319629272514d052e' \
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

