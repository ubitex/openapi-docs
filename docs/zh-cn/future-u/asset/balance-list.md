# 获取用户资金

`GET` /v1/future-u/user/balance/list

## 请求参数

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/balance/list' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514400888' \
--header 'validate-signature: 31e501408933f2042ec0b0c28b5e825962d1f348b423247ffaadacfec2c59242' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=8FF5A9153450BDA558BF120CD75F0632'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": [
        {
            "coin": "usdt",
            "walletBalance": "2499.57554469",
            "openOrderMarginFrozen": "0",
            "isolatedMargin": "0",
            "crossedMargin": "565.12545",
            "availableBalance": "1934.45009469",
            "bonus": "503",
            "coupon": "0"
        }
    ],
    "ts": 1725514401067
}
```

