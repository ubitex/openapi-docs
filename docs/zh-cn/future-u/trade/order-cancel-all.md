# 撤销所有订单

`POST` /v1/future-u/trade/v2/order/cancel-all

## 请求参数

| 名称   | 位置  | 类型   | 必选 | 说明                               |
| ------ | ----- | ------ | ---- | ---------------------------------- |
| symbol | query | string | 否   | 交易对（不传时撤销所有交易对订单） |


> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/v2/order/cancel-all?symbol=eth_usdt' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725621886571' \
--header 'validate-signature: 5dff96de6e5fba9c5fe0d91dac502c0b0e8488547abcb16f83740f64f7cd3599' \
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
  "ts": 1725621886737
}
```

