# Cancel batch order

`DELETE` /v1/spot/batch-order

## Request Parameters

| name            | location   | type     | required | Description          |
|---------------|------|--------|----|-------------|
| clientBatchId | body | string | Yes  | 客户端批次号      |
| symbol        | body | string | Yes  | symbol         |
| orderIds      | body | string | Yes  | 订单集合, <=300 |

> Request Example

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

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": null,
  "ts": 1724923978773
}
```

