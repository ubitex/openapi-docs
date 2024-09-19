# 是否已经开通合约

`GET` /v1/future-u/user/compat/account/open

## 请求参数

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/compat/account/open' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725637193085' \
--header 'validate-signature: 205c67ea79c1b1fe53e5ad2715d6331024813ef0dabcf26a80766c0ad0d36b2c' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": true,
    "ts": 1725514280247
}
```

