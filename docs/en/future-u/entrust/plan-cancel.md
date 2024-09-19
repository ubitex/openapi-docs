# Cancel Trigger Orders

`DELETE` /v1/future-u/trade/v2/entrust/cancel-plan

## Request Parameters

| name        | location    | type      | required | Description     |
|-----------|-------|---------|----|--------|
| entrustId | query | integer | No  | 计划委托id |

> Request Example

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/future-u/trade/v2/entrust/cancel-plan?entrustId=403350930451513536' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725868585602' \
--header 'validate-signature: 64f780ee11d14f9b9d82e53d7ae39daaa148d7cc87e7b7118b56ef46f08790ea' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": null,
    "data": "403350930451513536",
    "ts": 1725868586494
}
```

