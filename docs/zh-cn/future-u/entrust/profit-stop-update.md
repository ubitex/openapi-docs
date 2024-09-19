# 修改止盈止损

`POST` /v1/future-u/trade/v2/entrust/update-profit-stop

## 请求参数

| 名称                      | 位置 | 类型         | 必选  | 说明                                        |
| ------------------------- | ---- | ------------ | ----- | ------------------------------------------- |
| profitId                  | body | integer | true  | 止盈止损id                                        |
| triggerProfitPrice        | body | number  | false | 止盈触发价                                        |
| triggerStopPrice          | body | number  | false | 止损触发价                                        |
| triggerPriceType          | body | string  | false | 触发价格类型：INDEX_PRICE(指数价格); MARK_PRICE(标记价格)；LATEST_PRICE(最新价格)                                        |

> 请求示例

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/future-u/trade/v2/entrust/update-profit-stop' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725876765314' \
--header 'validate-signature: 217dd75468c495a0e0e216a3818587bd32c81d6621105cdfb025bb1c9e19e66d' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--data-raw '{"profitId":403374944700068900,"triggerPriceType":"INDEX_PRICE","triggerProfitPrice":56400,"triggerStopPrice":52100}'
```

## 响应结果

```json

```

