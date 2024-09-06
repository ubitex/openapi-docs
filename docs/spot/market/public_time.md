获取服务器信息

`GET` /v1/spot/public/time

## 请求参数

无


### 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/spot/public/time' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521209606' \
--header 'validate-signature: bd3273f6e4594f2b56600f3166809b8f613534f14c3bb77dfe76a3a26769e4dc' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' 
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": {
        "serverTime": 1725523397172
    },
    "ts": 1725523397172
}
```

