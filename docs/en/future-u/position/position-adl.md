# 获取ADL信息

`POST` /v1/future-u/trade/position/adl

## Request Parameters

| name           | location    | type     | required    | Description                            |
|--------------|-------|--------|-------|-------------------------------|
| symbol       | query | string | false | symbol                           |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/position/adl?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725702268736' \
--header 'validate-signature: e6132633c0d4623d24a95d93d794406f99491b80578c36cd1e4e3fdf5b4c1e9d' \
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
    "data": [],
    "ts": 1725702269399
}
```

