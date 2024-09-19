# 批量撤单

`DELETE` /v1/spot/batch-order

## 请求参数

| 名称            | 位置   | 类型     | 必选 | 说明          |
|---------------|------|--------|----|-------------|
| clientBatchId | body | string | 是  | 客户端批次号      |
| symbol        | body | string | 是  | 交易对         |
| orderIds      | body | string | 是  | 订单集合, <=300 |

> 请求示例

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/spot/batch-order' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725547188574' \
--header 'validate-signature: e968516d6e4a32a699a0b97df0f24c4c594da4b16d3ebe25f483bfbcb3f183e5' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=8FF5A9153450BDA558BF120CD75F0632' 
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

