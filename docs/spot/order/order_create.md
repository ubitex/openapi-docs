单笔下单

`POST` /v1/spot/order

## 请求参数

| 名称            | 类型     | 必选    | 约束   | 中文名 | 说明                                    |
|---------------|--------|-------|------|-----|---------------------------------------|
| symbol        | string | true  | none |     | 交易对                                   |
| clientOrderId | string | false | none |     | 客户端ID(最长32位)                          |
| side          | string | true  | none |     | 买卖方向,[枚举](/spot/README?id=买卖方向)       |
| type          | string | true  | none |     | 订单类型,[枚举](/spot/README?id=订单类型及含义)    |
| timeInForce   | string | true  | none |     | 有效方式,[枚举](/spot/README.md?id=BizType) |
| bizType       | string | true  | none |     | 业务类型,[枚举](/spot/README.md?id=BizType) |
| price         | number | false | none |     | 价格。现价必填; 市价不填                         |
| quantity      | number | false | none |     | 数量。现价必填；市价按数量下单时必填                    |
| quoteQty      | number | false | none |     | 金额。现价不填；市价按金额下单时必填                    |

> 请求示例

```shell
curl --location --request POST 'https://api.ubit.site/v1/spot/order' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725455266041' \
--header 'validate-signature: ce246607785e168d4677afff5af3746eb8513133d11ca3c5e3913eeea5aca63c' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' \
--data-raw '{"symbol":"BTC_USDT","clientOrderId":"16559590087220001","side":"BUY","type":"LIMIT","timeInForce":"FOK","bizType":"SPOT","price":40000,"quantity":2,"media":"btok","mediaChannel":"12345"}'
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

