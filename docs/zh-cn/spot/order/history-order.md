# 历史订单查询

`GET` /v1/spot/history-order

## 请求参数

| 名称             | 位置    | 类型      | 必选 | 说明                                                                                                       |
|----------------|-------|---------|----|----------------------------------------------------------------------------------------------------------|
| symbol         | query | string  | 否  | 交易对，不传代表所有                                                                                               |
| bizType        | query | string  | 否  | 业务类型，SPOT-现货                                                                                             |
| type           | query | string  | 否  | 订单类型，LIMIT-现价, MARKET-市价                                                                                 |
| side           | query | string  | 否  | 订单方向，BUY-买,SELL-卖                                                                                        |
| state          | query | string  | 否  | 状态，NEW-新建,PARTIALLY_FILLED-部分成交,FILLED-全部成交,CANCELED-用户撤单,REJECTED-下单失败,EXPIRED-过期(time_in_force撤单或溢价撤单) |
| fromId         | query | integer | 否  | 起始ID                                                                                                     |
| direction      | query | string  | 否  | 查询方向，PREV, NEXT                                                                                          |
| limit          | query | integer | 否  | 限制数量,最大100                                                                                               |
| startTime      | query | integer | 否  | 开始时间                                                                                                     |
| endTime        | query | integer | 否  | 结束时间                                                                                                     |
| hiddenCanceled | query | boolean | 否  | 隐藏已取消                                                                                                    |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/history-order?symbol=btc_usdt&bizType=SPOT&type&side&state&fromId&direction&limit&startTime&endTime&hiddenCanceled' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725549387826' \
--header 'validate-signature: e3644a62a00482963a2a2db98d8669cfca12d08790cb6d72c8aee4e617a9fa98' \
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
    "hasPrev": false,
    "hasNext": false,
    "items": [
      {
        "symbol": "btc_usdt",
        "orderId": "401927906947008832",
        "clientOrderId": "16559590087220001",
        "baseCurrency": "btc",
        "quoteCurrency": "usdt",
        "side": "BUY",
        "type": "LIMIT",
        "timeInForce": "GTC",
        "price": "40000.00",
        "origQty": "2.000000",
        "origQuoteQty": "80000.00",
        "executedQty": "0.000000",
        "leavingQty": "0.000000",
        "tradeBase": "0.000000",
        "tradeQuote": "0.00",
        "avgPrice": null,
        "fee": null,
        "feeCurrency": null,
        "closed": true,
        "state": "CANCELED",
        "time": 1725529080475,
        "updatedTime": 1725529090509
      },
      {
        "symbol": "btc_usdt",
        "orderId": "401893361514219840",
        "clientOrderId": "16559590087220001",
        "baseCurrency": "btc",
        "quoteCurrency": "usdt",
        "side": "BUY",
        "type": "MARKET",
        "timeInForce": "FOK",
        "price": null,
        "origQty": null,
        "origQuoteQty": "800.00",
        "executedQty": "799.98026982",
        "leavingQty": "0.00",
        "tradeBase": "0.013982",
        "tradeQuote": "799.98026982",
        "avgPrice": "57215.01",
        "fee": "0.00006991",
        "feeCurrency": "btc",
        "closed": true,
        "state": "FILLED",
        "time": 1725520844202,
        "updatedTime": 1725520844347
      }
    ]
  },
  "ts": 1725549388385
}
```

