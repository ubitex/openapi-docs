# Open Contract

`POST` /v1/future-u/user/account/open

## Request Parameters

> Request Example

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/user/account/open' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514280062' \
--header 'validate-signature: 3ccf3f0a8b26e05a7350415f09a05d85db667c3e90ff6786671f5dc909239c2c' \
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
    "data": true,
    "ts": 1725514280247
}
```

