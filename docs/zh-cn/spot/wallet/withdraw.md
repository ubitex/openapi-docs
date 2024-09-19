# 提现

`POST` /v1/spot/withdraw

## 请求参数

| 名称       | 位置   | 类型     | 必选    | 说明       |
|----------|------|--------|-------|----------|
| chain    | body | string | true  | 币种转账网络名称 |
| currency | body | string | true  | 币种名称     |
| amount   | body | number | true  | 提币金额     |
| address  | body | string | true  | 提币地址     |
| memo     | body | string | false | memo     |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/spot/withdraw' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725593554676' \
--header 'validate-signature: f99ced0740217110dd5cb1712943f9dad3da19ed79e8a520283f94c3a9aef29e' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"chain":"Tron","currency":"usdt","amount":10,"address":"TKr47rQg831zd1UAY3u5K71fXuXMEowFXW"}'
```

## 响应结果

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": null,
  "ts": 1724923978773
}
```

