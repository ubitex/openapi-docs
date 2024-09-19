# Change Position Type

`POST` /v1/future-u/trade/position/v2/change-type

## Request Parameters

| name           | location   | type          | required   | Description                            |
|--------------|------|-------------|------|-------------------------------|
| symbol       | body | string | true | symbol                           |
| positionSide | body | string | true | 仓位方向:LONG(多仓);SHORT(空仓)       |
| positionType | body | string | true | 仓位type:CROSSED(全仓);ISOLATED(逐仓) |

> Request Example

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/position/v2/change-type?symbol' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725703786421' \
--header 'validate-signature: b5d0b4360ee2f3afac4467b21b08edc2d4c9d37d166f00962a4ca8fb45f52ea4' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"symbol":"bnb_usdt","positionSide":"LONG","positionType":"CROSSED"}'
```

## Response Result

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": null,
    "ts": 1725703653244
}
```

