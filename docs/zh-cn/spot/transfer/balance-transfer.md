# 划转

`POST` /v1/spot/balance/transfer

## 请求参数

| 名称       | 位置   | 类型     | 必选    | 说明                                     |
|----------|------|--------|-------|----------------------------------------|
| bizId    | body | string | true  | 唯一id 用作重复请求幂等	                         |
| from     | body | string | true  | 划出业务账户 [bizType](../README?id=biztype) |
| to       | body | string | true  | 划入业务账户 [bizType](../README?id=biztype) |
| currency | body | string | true  | 划转币种                                   |
| symbol   | body | string | false | 划转交易对必须全部小写                            |
| amount   | body | number | true  | 划转的数量                                  |
| remark   | body | string | false | 备注                                     |
| toRemark | body | string | false | 备注                                     |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/spot/balance/transfer' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725593270606' \
--header 'validate-signature: 64c7b5083c41fc2f6670ac319b1d8bd75cdddd6d0e3e3ebdf2e78f1722d32244' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"bizId":1721515925613203,"from":"SPOT","to":"FUTURES_U","currency":"usdt","amount":"10","remak":"划转"}'
```

## 响应结果

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": 402197141623517376,
  "ts": 1725593271246
}
```

