# 资产总计转化

`GET` /v1/future-u/user/compat/balance/convert

## 请求参数

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/compat/balance/convert' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725637178380' \
--header 'validate-signature: 5b3eb7df0c93b03425d063fc15d7081e732c70bfb1d55b6bc6ed822c40ba43d3' \
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
    "data": {
        "coin": "btc",
        "convert": "0.03723601",
        "usdtConvert": "2020.9476"
    }
}
```

