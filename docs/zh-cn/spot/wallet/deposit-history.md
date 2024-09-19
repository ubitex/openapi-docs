# 充值历史

`GET` /v1/spot/deposit/history

## 请求参数

| 名称      | 位置  | 类型    | 必选 | 说明     |
| --------- | ----- | ------- | ---- | -------- |
| currency  | query | string  | 否   | 币种名称 |
| chain     | query | string  | 否   | 转账网络 |
| startTime | query | integer | 否   | 开始时间 |
| endTime   | query | integer | 否   | 结束时间 |
| status    | query | integer | 否   | 充值状态 |
| page      | query | integer | 否   | 页码     |
| size      | query | integer | 否   | 页大小   |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/deposit/history?currency=USDT&chain=Tron&startTime&endTime&status&page=1&size=10' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725611669282' \
--header 'validate-signature: 90748ca1bebe2529220a194f73f7696e6d1198d35971c586ec7f09a03d6a5243' \
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
        "hasPrev": null,
        "hasNext": null,
        "items": null
    },
    "ts": 1725611669358
}
```

