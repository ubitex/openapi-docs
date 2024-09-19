# Get history records of deposit

`GET` /v1/spot/deposit/history

## Request Parameters

| name      | location  | type    | required | Description     |
| --------- | ----- | ------- | ---- | -------- |
| currency  | query | string  | No   | coinname |
| chain     | query | string  | No   | 转账网络 |
| startTime | query | integer | No   | 开始时间 |
| endTime   | query | integer | No   | End Time |
| status    | query | integer | No   | 充值状态 |
| page      | query | integer | No   | 页码     |
| size      | query | integer | No   | 页大小   |

> Request Example

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

## Response Result

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

