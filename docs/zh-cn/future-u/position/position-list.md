# 获取持仓信息

`GET` /v1/future-u/trade/position/list

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明                                     |
| ------ | ----- | ------ | ---- | ---------------------------------------- |
| symbol | query | string | 否   | 交易对（不传时查询所有交易对的持仓信息） |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/position/list?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514676647' \
--header 'validate-signature: 81b6d674283765fae72071e5dfd19052c33691683ae613039c670453938be948' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' 
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": [
        {
            "symbol": "btc_usdt",
            "positionType": "CROSSED",
            "positionSide": "LONG",
            "contractType": "PERPETUAL",
            "positionSize": "1977",
            "closeOrderSize": "0",
            "availableCloseSize": "1977",
            "entryPrice": "57170",
            "openOrderSize": "0",
            "isolatedMargin": "565.12545",
            "openOrderMarginFrozen": "0",
            "realizedProfit": "3.35705009",
            "autoMargin": false,
            "leverage": 20,
            "profitId": null,
            "triggerPriceType": null,
            "triggerProfitPrice": null,
            "triggerStopPrice": null,
            "welfareAccount": false
        }
    ],
    "ts": 1725514676797
}
```

