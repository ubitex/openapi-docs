# 撤销所有计划委托

`DELETE` /v1/future-u/trade/v2/entrust/cancel-all-plan

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明                           |
| ------ | ----- | ------ | ---- | ------------------------------ |
| symbol | query | string | 否   | 交易对（不传时撤销所有交易对） |

> 请求示例

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/future-u/trade/v2/entrust/cancel-all-plan?symbol=btc_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725869767691' \
--header 'validate-signature: cc623ace7fc0488e6dcff43ff58317f569cf8d82dcb6dbd6b784296342c2e8d2' \
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
    "data": true,
    "ts": 1725869768192
}
```

