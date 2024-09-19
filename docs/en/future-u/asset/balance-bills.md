# Get User's Account Flow Information

`GET` /v1/future-u/user/balance/bills

## Request Parameters

| name        | location    | type      | required | Description                                                                                                                                                       |
|-----------|-------|---------|----|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol    | query | string  | No  | symbol                                                                                                                                                      |
| id        | query | integer | No  | none                                                                                                                                                     |
| direction | query | string  | Yes  | Direction (PREV: previous page; NEXT: Next page)                                                                                                                                    |
| limit     | query | integer | Yes  | Page Limit                                                                                                                                                       |
| coin      | query | string  | No  | coin                                                                                                                                                       |
| type      | query | string  | No  | EXCHANGE: transfer; CLOSE_POSITION: Close profit and loss; TAKE_OVER: position takeover; QIANG_PING_MANAGER: Qiangping management fee (handling fee); FUND: the cost of capital; FEE: Handling fee (opening, closing, strong closing); ADL: automatic stock reduction; MERGE: Position merge; SYSTEM_CLOSE_POSITION: The system closes the position |
| startTime | query | integer | No  | Start Time                                                                                                                                                     |
| endTime   | query | integer | No  | End Time                                                                                                                                                     |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/balance/bills?symbol=btc_usdt&id&direction=NEXT&limit=10&coin&type&startTime&endTime' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725514474787' \
--header 'validate-signature: 00f5c33e3c0f2610e3103b5bff81b255a046d68576cd40b99d187a0006a67229' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=8FF5A9153450BDA558BF120CD75F0632'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": {
    "hasPrev": false,
    "hasNext": false,
    "items": [
      {
        "id": "401857946532741376",
        "accountId": 45756045342,
        "coin": "usdt",
        "symbol": "btc_usdt",
        "type": "FUND",
        "amount": "3.3570",
        "side": "ADD",
        "afterAmount": "2499.5755",
        "createdTime": 1725512400613,
        "balanceBonusDetailVO": {
          "orderId": null,
          "execId": null,
          "amount": "3.35705009",
          "couponAmount": "0",
          "bonusAmount": "0",
          "realAmount": "3.35705009",
          "timestamp": null
        }
      },
      {
        "id": "401857871265956099",
        "accountId": 45756045342,
        "coin": "usdt",
        "symbol": "btc_usdt",
        "type": "FEE",
        "amount": "-6.7815",
        "side": "SUB",
        "afterAmount": "2496.2184",
        "createdTime": 1725512382668,
        "balanceBonusDetailVO": {
          "orderId": null,
          "execId": null,
          "amount": "-6.7815054",
          "couponAmount": "0",
          "bonusAmount": "6.7815054",
          "realAmount": "0",
          "timestamp": null
        }
      }
    ]
  },
  "ts": 1725514474978
}
```

