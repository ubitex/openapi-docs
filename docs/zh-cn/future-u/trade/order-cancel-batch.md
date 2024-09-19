# 批量撤订

`POST` /v1/future-u/trade/v2/order/cancel-batch

## 请求参数

| 名称             | 位置   | 类型   | 必选    | 说明                   |
|----------------|------|------|-------|----------------------|
| orderIds       | body | list | false | 订单ID集合，任意传其中一个       |
| clientOrderIds | body | list | false | 自定义orderId集合，任意传其中一个 |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/v2/order/cancel-batch' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725621978205' \
--header 'validate-signature: cc03657b70bc7980c988ecafb231063ccc752898a5bde0589594f97132414810' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"orderIds":["402317447499403328"],"clientOrderIds":["23121"]}'
```

## 响应结果

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": true,
  "ts": 1725621978556
}
```

