# 获取用户阶梯费率

`GET` /v1/future-u/user/user/step-rate

## 请求参数

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/user/step-rate' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514822675' \
--header 'validate-signature: 4c1ac90b4431fe43807fe3e0cb1d5c8388a9ded21016496b33af8158aacd6e15' \
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
    "data": {
        "specialType": false,
        "discountLevel": 0,
        "makerFee": "0.0004",
        "takerFee": "0.0006",
        "levelReturnDay": 364,
        "totalTradeVolume": "0",
        "uBasedTotalTradeVolume": "0",
        "coinBasedTotalTradeVolume": "0",
        "nextLvTradeVolume": "200000",
        "lackTradeVolume": "200000",
        "nextLvMakerFee": "0.00038",
        "nextLvTakerFee": "0.000588",
        "ubasedTotalTradeVolume": 0E-18
    },
    "ts": 1725514823369
}
```

