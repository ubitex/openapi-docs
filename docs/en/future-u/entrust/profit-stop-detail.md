# Query Stop Limit By profitId

`GET` /v1/future-u/trade/entrust/profit-detail

## Request Parameters

| name       | location    | type      | required | Description     |
|----------|-------|---------|----|--------|
| profitId | query | integer | Yes  | 止盈止损id |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/entrust/profit-detail?profitId=403374944700068928' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725874929540' \
--header 'validate-signature: 268ac27b1d13430a562ddd2238721d389fe0b82e72188d0096fa7083eecb5815' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": {
        "profitId": "403374944700068928",
        "symbol": "btc_usdt",
        "positionSide": "LONG",
        "origQty": "1",
        "triggerPriceType": "INDEX_PRICE",
        "triggerProfitPrice": "56300",
        "triggerStopPrice": "52000",
        "entryPrice": null,
        "positionSize": null,
        "isolatedMargin": null,
        "executedQty": null,
        "avgPrice": null,
        "positionType": "CROSSED",
        "delegateQty": null,
        "delegatePrice": null,
        "profitDelegateOrderType": "MARKET",
        "profitDelegateTimeInForce": "IOC",
        "profitDelegatePrice": null,
        "stopDelegateOrderType": "MARKET",
        "stopDelegateTimeInForce": "IOC",
        "stopDelegatePrice": null,
        "closeType": "FIXED",
        "state": "USER_REVOCATION",
        "desc": "user_revocation",
        "triggerPriceSide": "PROFIT",
        "createdTime": 1725874081207,
        "updatedTime": 1725874886660
    },
    "ts": 1725874929821
}
```

