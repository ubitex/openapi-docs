# Get Market Information for Specific Trading Pair

`GET` /v1/future-u/market/public/q/ticker

## Request Parameters

| name     | location    | type     | required | Description  |
|--------|-------|--------|----|-----|
| symbol | query | string | Yes  | symbol |

> Request Example

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/market/public/q/ticker?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725508200475' \
--header 'validate-signature: 6011cb6f8b894c4ececdced5bd3c9a8a13dfdc388c92a07a4a20eed16837c6d7' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": {
    "t": 1725508199938,
    "s": "btc_usdt",
    "c": "57103.85",
    "h": "58498.95",
    "l": "56156.15",
    "a": "529621200",
    "v": "3042556369",
    "o": "57702.70",
    "r": "-0.0103"
  },
  "ts": 1725508201420
}
```

