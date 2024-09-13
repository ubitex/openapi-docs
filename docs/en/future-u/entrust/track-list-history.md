# 查询历史跟踪委托

`GET` /trade/entrust/track-list-history

## Request Parameters

| name        | location    | type      | required | Description                                                                                                                                                                  |
|-----------|-------|---------|----|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | No  | symbol                                                                                                                                                                 |
| id        | query | integer | No  | none                                                                                                                                                                |
| direction | query | string  | Yes  | Direction (PREV: previous page; NEXT: Next page)                                                                                                                                               |
| limit     | query | integer | Yes  | Page Limit                                                                                                                                                                  |
| startTime | query | integer | No  | Start Time                                                                                                                                                                |
| endTime   | query | integer | No  | End Time                                                                                                                                                                |
| state     | query | string  | No  | 订单状态 NOT_ACTIVATION: 未激活；NOT_TRIGGERED：新建委托（未触发）；TRIGGERING：触发中；TRIGGERED：已触发；USER_REVOCATION：用户撤销；PLATFORM_REVOCATION：平台撤销（拒绝）；EXPIRED：已过期;DELEGATION_FAILED: 委托失败 |

> Request Example

```shell

```

## Response Result

```json

```

