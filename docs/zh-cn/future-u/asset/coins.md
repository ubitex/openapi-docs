# 划转币种列表

`GET` /v1/future-u/user/public/compat/coins

## 请求参数

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/public/compat/coins' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725637159471' \
--header 'validate-signature: b00728c49dd0bf88607b1aca3bbfdb56655fb566ebae48b0a34adf4a0bda8210' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "SUCCESS",
    "msgInfo": [],
    "data": [
        "usdt"
    ]
}
```

