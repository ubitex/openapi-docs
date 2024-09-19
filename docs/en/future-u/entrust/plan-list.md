# Query Trigger Orders

`GET` /v1/future-u/trade/entrust/plan-list

## Request Parameters

| name      | location | type    | required | Description                                                                                                                                                                                                                                                                              |
|-----------|----------|---------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query    | string  | No       | symbol                                                                                                                                                                                                                                                                                   |
| page      | query    | integer | No       | page                                                                                                                                                                                                                                                                                     |
| size      | query    | integer | No       | page size                                                                                                                                                                                                                                                                                |
| startTime | query    | integer | No       | Start Time                                                                                                                                                                                                                                                                               |
| endTime   | query    | integer | No       | End Time                                                                                                                                                                                                                                                                                 |
| state     | query    | string  | No       | Delegation status NOT_TRIGGERED: New delegation was triggered (not triggered). TRIGGERING: triggering; TRIGGERED: triggered; USER_REVOCATION: User vocation; PLATFORM_REVOCATION: platform vocation revoked (rejected); EXPIRED: Has expired; UNFINISHED: Unfinished. HISTORY: (History) |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/trade/entrust/plan-list?page=1&size=10&symbol=btc_usdt&startTime&endTime&state' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725513605241' \
--header 'validate-signature: 2525119ba9e623cb5a1e7d909e424d915bbee998114cf567480986bec644c789' \
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
  "data": {
    "page": 1,
    "ps": 10,
    "total": 1,
    "items": [
      {
        "entrustId": "401862973001741632",
        "symbol": "btc_usdt",
        "entrustType": "TAKE_PROFIT",
        "orderSide": "BUY",
        "positionSide": "LONG",
        "timeInForce": "GTC",
        "closePosition": null,
        "price": "57115.65",
        "origQty": "1936",
        "stopPrice": "50000",
        "triggerPriceType": "LATEST_PRICE",
        "executedQty": null,
        "avgPrice": null,
        "state": "NOT_TRIGGERED",
        "marketOrderLevel": null,
        "createdTime": 1725513599041,
        "updatedTime": 1725513599041,
        "ordinary": false
      }
    ]
  },
  "ts": 1725513605454
}
```

