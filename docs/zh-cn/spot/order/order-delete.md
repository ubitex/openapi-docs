# 单笔撤单

`DELETE` /v1/spot/order/{orderId}

## 请求参数

| 名称      | 位置   | 类型     | 必选 | 说明   |
|---------|------|--------|----|------|
| orderId | path | string | 是  | 订单ID |

> 请求示例

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/spot/order/401629267720702272' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725497723734' \
--header 'validate-signature: d419869b44a00df20c74e340613f543524014ce85f25bcde38c2fe7a4c027a07' \
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
    "orderId": "401618309946313024",
    "clientOrderId": "16559590087220001"
  },
  "ts": 1725455266831
}
```

