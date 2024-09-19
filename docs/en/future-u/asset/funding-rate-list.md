# Get Fund Fee Information

`GET` /v1/future-u/user/balance/funding-rate-list

## Request Parameters

| name        | location    | type      | required | Description                    |
|-----------|-------|---------|----|-----------------------|
| symbol    | query | string  | No  | symbol                   |
| id        | query | integer | No  | none                  |
| direction | query | string  | No  | Direction (PREV: previous page; NEXT: Next page) |
| limit     | query | integer | No  | Page Limit                    |
| startTime | query | integer | No  | Start Time                  |
| endTime   | query | integer | No  | End Time                  |

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/user/balance/funding-rate-list?symbol=&id&direction=NEXT&limit=20&startTime&endTime' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725693243052' \
--header 'validate-signature: de0de42edbda4e18eacee3d27aac7f3e38f2b0f9a951982c91709c55c739a469' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=CBA75C7DDBA9F5C552D6482C0FECB0A6'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": null,
  "data": {
    "hasPrev": false,
    "hasNext": true,
    "items": [
      {
        "id": "402612921022021632",
        "symbol": "btc_usdt",
        "cast": "-0.3257",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725692400558
      },
      {
        "id": "402612920946524160",
        "symbol": "btc_usdt",
        "cast": "3.5127",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725692400540
      },
      {
        "id": "402597819417886721",
        "symbol": "btc_usdt",
        "cast": "-0.3248",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725688800055
      },
      {
        "id": "402597819346583552",
        "symbol": "btc_usdt",
        "cast": "3.504",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725688800038
      },
      {
        "id": "402582719957041152",
        "symbol": "btc_usdt",
        "cast": "-0.3241",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725685200063
      },
      {
        "id": "402582719885737984",
        "symbol": "btc_usdt",
        "cast": "3.4959",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725685200046
      },
      {
        "id": "402567620554915840",
        "symbol": "btc_usdt",
        "cast": "-0.2958",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725681600085
      },
      {
        "id": "402567620483612672",
        "symbol": "btc_usdt",
        "cast": "3.1906",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725681600068
      },
      {
        "id": "402552520959852544",
        "symbol": "btc_usdt",
        "cast": "-0.3226",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725678000061
      },
      {
        "id": "402552520888549376",
        "symbol": "btc_usdt",
        "cast": "3.4799",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725678000044
      },
      {
        "id": "402537421452869632",
        "symbol": "btc_usdt",
        "cast": "-0.3227",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725674400058
      },
      {
        "id": "402537421381566464",
        "symbol": "btc_usdt",
        "cast": "3.4807",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725674400041
      },
      {
        "id": "402522321941692416",
        "symbol": "btc_usdt",
        "cast": "-0.3233",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725670800054
      },
      {
        "id": "402522321870389248",
        "symbol": "btc_usdt",
        "cast": "3.4871",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725670800037
      },
      {
        "id": "402507222514401280",
        "symbol": "btc_usdt",
        "cast": "-0.3235",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725667200070
      },
      {
        "id": "402507222443098112",
        "symbol": "btc_usdt",
        "cast": "3.4898",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725667200053
      },
      {
        "id": "402507222287908864",
        "symbol": "eth_usdt",
        "cast": "-0.7828",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725667200016
      },
      {
        "id": "402492148047413248",
        "symbol": "btc_usdt",
        "cast": "-0.3216",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725663606037
      },
      {
        "id": "402492147976110080",
        "symbol": "btc_usdt",
        "cast": "3.4695",
        "coin": "usdt",
        "positionSide": "LONG",
        "createdTime": 1725663606020
      },
      {
        "id": "402477023462686720",
        "symbol": "btc_usdt",
        "cast": "-0.3224",
        "coin": "usdt",
        "positionSide": "SHORT",
        "createdTime": 1725660000055
      }
    ]
  },
  "ts": 1725693244218
}
```

