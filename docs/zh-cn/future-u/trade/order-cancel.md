# 撤销订单

`POST` /v1/future-u/trade/v2/order/cancel

## 请求参数

| 名称            | 位置   | 类型           | 必选    | 说明                  |
|---------------|------|--------------|-------|---------------------|
| orderId       | body | integer | false | 订单id，任意传其中一个        |
| clientOrderId | body | string  | false | client 订单id，任意传其中一个 |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/v2/order/cancel' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725607411560' \
--header 'validate-signature: 41c559c23f316df4e50bce85bff33e394d7348c8cfefd15c529a42175b610b30' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"clientOrderId":"1232323232"}'

```

## 响应结果

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": "402256315363332992",
  "ts": 1725607411720
}
```

