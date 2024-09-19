# 调整杠杆倍数

`POST` /v1/future-u/trade/position/v2/adjust-leverage

## 请求参数

| 名称           | 位置   | 类型           | 必选   | 说明   |
|--------------|------|--------------|------|------|
| symbol       | body | string  | true | 交易对  |
| positionSide | body | string  | true | 仓位方向 |
| leverage     | body | integer | true | 杠杆倍数 |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/position/v2/adjust-leverage' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725703648876' \
--header 'validate-signature: 7684383075b664e64d55f4359ff2e919894724f1e43e778a569397fac013fda2' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"symbol":"btc_usdt","positionSide":"LONG","leverage":20}'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": null,
    "ts": 1725703653244
}
```

