# 撤销所有止盈止损

`DELETE` /v1/future-u/trade/v2/entrust/cancel-all-profit-stop

## 请求参数

| 名称     | 位置    | 类型     | 必选 | 说明              |
|--------|-------|--------|----|-----------------|
| symbol | query | string | 否  | 交易对（不传时撤销所有交易对） |

> 请求示例

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/future-u/trade/v2/entrust/cancel-all-profit-stop?symbol' \
--header 'User-Agent: Apifox/1.0.0 (https://apifox.com)' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725874898501' \
--header 'validate-signature: 124e3744371b5098cf01a6c8529c6bf2a53d64aeebae43a873749364c6ec6f8b' \
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
    "ts": 1725874898763
}
```

