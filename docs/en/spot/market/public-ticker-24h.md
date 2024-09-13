# Get 24h statistics ticker

`GET` /v1/spot/public/ticker/24h

## Request Parameters

| name    | location  | type          | required | Description                         |
| ------- | ----- | ------------- | ---- | ---------------------------- |
| symbol  | query | string        | No   | symbol                       |
| symbols | query | array[string] | No   | symbol集合，不传时，返回全量 |
| tags    | query | string        | No   | 标签集合                     |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/spot/public/ticker/24h?symbol=btc_usdt&symbols=&tags' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521583202' \
--header 'validate-signature: 6d7a821004badac4bf5beefc78b7e4edc72cea2ca31828f33a494031986d272f' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
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

