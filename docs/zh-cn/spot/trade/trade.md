# 成交查询

`GET` /v1/spot/trade

## 请求参数

| 名称        | 位置    | 类型      | 必选 | 说明                           |
|-----------|-------|---------|----|------------------------------|
| symbol    | query | string  | 否  | 交易对                          |
| orderSide | query | string  | 否  | 订单方向,[枚举](../README?id=买卖方向) |
| orderType | query | string  | 否  | 订单类型,[枚举](../README?id=订单类型) |
| bizType   | query | string  | 否  | 业务类型,SPOT-现货                 |
| orderId   | query | integer | 否  | 订单号                          |
| fromId    | query | integer | 否  | 分页起始                         |
| direction | query | string  | 否  | 方向                           |
| startTime | query | integer | 否  | 开始时间                         |
| endTime   | query | integer | 否  | 结束时间                         |
| limit     | query | integer | 否  | 限制数量,最大100                   |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/trade?symbol&orderSide&orderType&bizType=SPOT&orderId&fromId&direction&startTime=&endTime=&limit=20' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725589345948' \
--header 'validate-signature: a4df6afab3d8e58e35f4ec0e5076be6b15281a40c67641f4ab5efbf98ab6400b' \
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
        "tradeId": "401893362120038786",
        "orderId": "401893361514219840",
        "orderSide": "BUY",
        "orderType": "MARKET",
        "bizType": "SPOT",
        "time": 1725520844347,
        "price": "57215.01",
        "quantity": "0.013982",
        "quoteQty": "799.98026982",
        "baseCurrency": "btc",
        "quoteCurrency": "usdt",
        "fee": "0.00006991",
        "feeCurrency": "btc",
        "takerMaker": "TAKER",
        "realFeeAmount": "0.000034955",
        "deductFeeAmount": "0.000034955",
        "deductFeeCurrency": "btc",
        "useCouponAmount": "1.99995067",
        "useCouponCurrency": "usdt",
        "useCouponId": "397564044877249728"
      },
      {
        "symbol": "btc_usdt",
        "tradeId": "401892565407799682",
        "orderId": "401892565175273792",
        "orderSide": "BUY",
        "orderType": "MARKET",
        "bizType": "SPOT",
        "time": 1725520654396,
        "price": "57194.64",
        "quantity": "0.013987",
        "quoteQty": "799.98142968",
        "baseCurrency": "btc",
        "quoteCurrency": "usdt",
        "fee": "0.000069935",
        "feeCurrency": "btc",
        "takerMaker": "TAKER",
        "realFeeAmount": "0.0000349675",
        "deductFeeAmount": "0.0000349675",
        "deductFeeCurrency": "btc",
        "useCouponAmount": "1.99995357",
        "useCouponCurrency": "usdt",
        "useCouponId": "397564044877249728"
      }
    ]
  },
  "ts": 1725589346080
}
```

