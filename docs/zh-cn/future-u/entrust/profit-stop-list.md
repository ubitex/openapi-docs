# 查询止盈止损

`GET` /trade/entrust/profit-list

## 请求参数

| 名称        | 位置    | 类型      | 必选 | 说明                                                                                                                                                  |
|-----------|-------|---------|----|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | 否  | 交易对                                                                                                                                                 |
| page      | query | integer | 否  | 页码                                                                                                                                                  |
| size      | query | integer | 否  | 单页数                                                                                                                                                 |
| startTime | query | integer | 否  | 起始时间                                                                                                                                                |
| endTime   | query | integer | 否  | 结束时间                                                                                                                                                |
| state     | query | string  | 否  | 委托状态 NOT_TRIGGERED：新建委托（未触发）；TRIGGERING：触发中；TRIGGERED：已触发；USER_REVOCATION：用户撤销；PLATFORM_REVOCATION：平台撤销（拒绝）；EXPIRED：已过期；UNFINISHED：未完成；HISTORY：（历史） |

> 请求示例

```shell

```

## 响应结果

```json

```

