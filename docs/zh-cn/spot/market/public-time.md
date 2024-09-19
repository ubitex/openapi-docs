# 获取服务器时间

`GET` /v1/spot/public/time

## 请求参数

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/time' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
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

