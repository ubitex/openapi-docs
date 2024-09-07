获取用户账务流水

`GET` /v1/future-u/user/balance/bills

## 请求参数

| 名称      | 位置  | 类型    | 必选 | 说明                                                         |
| --------- | ----- | ------- | ---- | ------------------------------------------------------------ |
| symbol    | query | string  | 否   | 交易对                                                       |
| id        | query | integer | 否   | none                                                         |
| direction | query | string  | 是   | 方向（PREV:上一页；NEXT:下一页）                             |
| limit     | query | integer | 是   | 条数                                                         |
| coin      | query | string  | 否   | 币种                                                         |
| type      | query | string  | 否   | EXCHANGE:划转;CLOSE_POSITION:平仓盈亏;TAKE_OVER:仓位接管;QIANG_PING_MANAGER:强平清算费（手续费）;FUND:资金费用;FEE:手续费 (开仓、平仓、强平);ADL:自动减仓MERGE:仓位合并 |
| startTime | query | integer | 否   | 起始时间                                                     |
| endTime   | query | integer | 否   | 结束时间                                                     |

> type
```
EXCHANGE:划转;
CLOSE_POSITION:平仓盈亏;
TAKE_OVER:仓位接管;
QIANG_PING_MANAGER:强平清算费（手续费）;
FUND:资金费用;
FEE:手续费 (开仓、平仓、强平);
ADL:自动减仓
MERGE:仓位合并
EXCHANGE :EXCHANGE
CLOSE_POSITION :CLOSE_POSITION
TAKE_OVER :TAKE_OVER
QIANG_PING_MANAGER :QIANG_PING_MANAGER
FUND :FUND
FEE :FEE
ADL :ADL
FICTITIOUS :FICTITIOUS
MERGE :MERGE
SYSTEM_CLOSE_POSITION :SYSTEM_CLOSE_POSITION
CASH_BACK :CASH_BACK
DELIVERY_FEE :DELIVERY_FEE
SYSTEM_ADD :SYSTEM_ADD
BONUS_GRANT :BONUS_GRANT
BONUS_TAKE_BACK :BONUS_TAKE_BACK
BONUS_DEDUCTION :BONUS_DEDUCTION
LARGE_ACCOUNT_BONUS_GRANT :LARGE_ACCOUNT_BONUS_GRANT
LARGE_ACCOUNT_BONUS_TAKE_BACK :LARGE_ACCOUNT_BONUS_TAKE_BACK
BONUS_GRANT_AND_TAKE_BACK :BONUS_GRANT_AND_TAKE_BACK
BONUS_COUPON_GRANT :BONUS_COUPON_GRANT
BONUS_COUPON_RECOVERY :BONUS_COUPON_RECOVERY
BONUS_COUPON_PROFIT :BONUS_COUPON_PROFIT
AFFILIATE_KICKBACK :AFFILIATE_KICKBACK
COPY_TRADE_LEADER_PROFIT :COPY_TRADE_LEADER_PROFIT
COPY_TRADE_FOLLOWER_PROFIT :COPY_TRADE_FOLLOWER_PROFIT
COPY_TRADE_FOLLOWER_PROFIT_BACK :COPY_TRADE_FOLLOWER_PROFIT_BACK
COPY_TRADE_PLATFORM_LEADER_PROFIT :COPY_TRADE_PLATFORM_LEADER_PROFIT
```

> 请求示例

```shell
curl --location --request GET 'https://api.ubit.site/v1/future-u/user/balance/bills?symbol=btc_usdt&id&direction=NEXT&limit=10&coin&type&startTime&endTime' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514474787' \
--header 'validate-signature: 00f5c33e3c0f2610e3103b5bff81b255a046d68576cd40b99d187a0006a67229' \
--header 'Accept: */*' \
--header 'Host: api.ubit.site' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=8FF5A9153450BDA558BF120CD75F0632'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": {
        "hasPrev": false,
        "hasNext": false,
        "items": [
            {
                "id": "401857946532741376",
                "accountId": 45756045342,
                "coin": "usdt",
                "symbol": "btc_usdt",
                "type": "FUND",
                "amount": "3.3570",
                "side": "ADD",
                "afterAmount": "2499.5755",
                "createdTime": 1725512400613,
                "balanceBonusDetailVO": {
                    "orderId": null,
                    "execId": null,
                    "amount": "3.35705009",
                    "couponAmount": "0",
                    "bonusAmount": "0",
                    "realAmount": "3.35705009",
                    "timestamp": null
                }
            },
            {
                "id": "401857871265956099",
                "accountId": 45756045342,
                "coin": "usdt",
                "symbol": "btc_usdt",
                "type": "FEE",
                "amount": "-6.7815",
                "side": "SUB",
                "afterAmount": "2496.2184",
                "createdTime": 1725512382668,
                "balanceBonusDetailVO": {
                    "orderId": null,
                    "execId": null,
                    "amount": "-6.7815054",
                    "couponAmount": "0",
                    "bonusAmount": "6.7815054",
                    "realAmount": "0",
                    "timestamp": null
                }
            }
        ]
    },
    "ts": 1725514474978
}
```

