# 提现历史

`GET` /v1/spot/withdraw/history

## 请求参数
| 名称      | 位置  | 类型    | 必选 | 说明                    |
| --------- | ----- | ------- | ---- | ----------------------- |
| currency  | query | string  | 是   | 币种名称                |
| chain     | query | string  | 是   | 转账网络                |
| status    | query | string  | 否   | 提币状态 SUBMIT :SUBMIT |
| fromId    | query | integer | 否   | 上次开始的分页 Id       |
| direction | query | string  | 否   | 分页方向 PREV :PREV     |
| limit     | query | integer | 否   | 分页条数                |
| startTime | query | integer | 否   | 开始时间                |
| endTime   | query | integer | 否   | 结束时间                |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/withdraw/history?currency=usdt&chain=Tron&status&fromId&direction=NEXT&limit=10&startTime&endTime' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725590621414' \
--header 'validate-signature: 689e4025364635f5b4aca0b9013d947a913c25305227ea144dc8f299d8a4d827' \
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
    "data": {
        "hasPrev": false,
        "hasNext": false,
        "items": [
            {
                "id": 198059639915548949,
                "currency": "usdt",
                "chain": "Tron",
                "address": "TKr47rQg831zd1UAY3u5K71fXuXMEowFXW",
                "memo": "",
                "status": "REVIEW",
                "amount": "10",
                "fee": "2",
                "confirmations": 0,
                "transactionId": "",
                "createdTime": 1725589720000
            },
            {
                "id": 198059639915548948,
                "currency": "usdt",
                "chain": "Tron",
                "address": "TKr47rQg831zd1UAY3u5K71fXuXMEowFXW",
                "memo": "",
                "status": "REVIEW",
                "amount": "10",
                "fee": "2",
                "confirmations": 0,
                "transactionId": "",
                "createdTime": 1725589637000
            },
            {
                "id": 198059639915548947,
                "currency": "usdt",
                "chain": "Tron",
                "address": "TKr47rQg831zd1UAY3u5K71fXuXMEowFXW",
                "memo": "",
                "status": "REVIEW",
                "amount": "10",
                "fee": "2",
                "confirmations": 0,
                "transactionId": "",
                "createdTime": 1725589582000
            },
            {
                "id": 198059639915548946,
                "currency": "usdt",
                "chain": "Tron",
                "address": "TKr47rQg831zd1UAY3u5K71fXuXMEowFXW",
                "memo": "",
                "status": "REVIEW",
                "amount": "10",
                "fee": "2",
                "confirmations": 0,
                "transactionId": "",
                "createdTime": 1725589475000
            },
            {
                "id": 198059639915548943,
                "currency": "usdt",
                "chain": "Tron",
                "address": "TKr47rQg831zd1UAY3u5K71fXuXMEowFXW",
                "memo": "",
                "status": "REVIEW",
                "amount": "10",
                "fee": "2",
                "confirmations": 0,
                "transactionId": "",
                "createdTime": 1725533973000
            }
        ]
    },
    "ts": 1725590622021
}
```

