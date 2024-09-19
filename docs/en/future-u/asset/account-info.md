# 获取账户相关信息

`GET` /v1/future-u/user/account/info

## Request Parameters

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/account/info' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514253040' \
--header 'validate-signature: d22b97ee1a49ea021f79c801180bec0b52777e28f3e07bcf83033b8cecd30c1e' \
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
        "accountId": 45756045342,
        "userId": 45756045342,
        "userGroupId": 1,
        "allowTransfer": true,
        "allowTrade": true,
        "allowOpenPosition": true,
        "openTime": "2024-06-23T02:58:12",
        "state": 0
    },
    "ts": 1725514253223
}
```

