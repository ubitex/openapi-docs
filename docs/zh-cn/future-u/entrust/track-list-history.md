# 查询历史跟踪委托

`GET` /trade/entrust/track-list-history

## 请求参数

| 名称        | 位置    | 类型      | 必选 | 说明                                                                                                                                                                  |
|-----------|-------|---------|----|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | 否  | 交易对                                                                                                                                                                 |
| id        | query | integer | 否  | none                                                                                                                                                                |
| direction | query | string  | 是  | 方向（PREV:上一页；NEXT:下一页）                                                                                                                                               |
| limit     | query | integer | 是  | 条数                                                                                                                                                                  |
| startTime | query | integer | 否  | 起始时间                                                                                                                                                                |
| endTime   | query | integer | 否  | 结束时间                                                                                                                                                                |
| state     | query | string  | 否  | 订单状态 NOT_ACTIVATION: 未激活；NOT_TRIGGERED：新建委托（未触发）；TRIGGERING：触发中；TRIGGERED：已触发；USER_REVOCATION：用户撤销；PLATFORM_REVOCATION：平台撤销（拒绝）；EXPIRED：已过期;DELEGATION_FAILED: 委托失败 |

> 请求示例

```shell

```

## 响应结果

```json

```

