# 修改保证金

`POST` /v1/future-u/trade/position/v2/margin

## 请求参数

| 名称           | 位置   | 类型     | 必选   | 说明                            |
|--------------|------|--------|------|-------------------------------|
| symbol       | body | string | true | 交易对                           |
| positionSide | body | string | true | 持仓方向：LONG;SHORT               |
| margin       | body | number | true | 数量                            |
| type         | body | string | true | 调整方向（ADD：增加逐仓保证金；SUB：减少逐仓保证金） |

> 请求示例

```shell
curl --location --request POST 'https://api.ubitex.com/v1/future-u/trade/position/v2/margin' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725703884766' \
--header 'validate-signature: 2221b8cbeeafddf165ed5ce279dcec4f099c962ab6b363f28b3ece89604f7023' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"symbol":"BTC_USDT","positionSide":"LONG","margin":101,"type":"ADD"}'
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": null,
    "ts": 1725703653244
}
```

