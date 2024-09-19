# Get Market Information for Specific Trading Pair

`GET` /v1/future-u/market/public/q/ticker

## Request Parameters

| name   | location | type   | required | Description |
|--------|----------|--------|----------|-------------|
| symbol | query    | string | Yes      | symbol      |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/ticker?symbol=btc_usdt' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
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

