# Get Depth Data of Trading Pairs

`GET` /v1/future-u/market/public/q/depth

## Request Parameters

| name   | location  | type    | required | Description                 |
| ------ | ----- | ------- | ---- | -------------------- |
| symbol | query | string  | Yes   | symbol               |
| level  | query | integer | Yes   | 档位（min:1,max:50） |

Note：This method does not require a signature.

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/q/depth?symbol=btc_usdt&level=10' \
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
    "t": 1725624567033,
    "s": "btc_usdt",
    "u": 957285959306,
    "b": [
      [
        "55887.7",
        "11139"
      ],
      [
        "55887.54",
        "10355"
      ],
      [
        "55887.38",
        "15478"
      ],
      [
        "55887.22",
        "4615"
      ],
      [
        "55887.06",
        "964"
      ],
      [
        "55886.9",
        "10921"
      ],
      [
        "55886.74",
        "17504"
      ],
      [
        "55886.58",
        "100859"
      ],
      [
        "55886.44",
        "44163"
      ],
      [
        "55886.3",
        "47764"
      ]
    ],
    "a": [
      [
        "55887.8",
        "6525"
      ],
      [
        "55887.96",
        "3128"
      ],
      [
        "55888.12",
        "8412"
      ],
      [
        "55888.28",
        "14826"
      ],
      [
        "55888.44",
        "11756"
      ],
      [
        "55888.6",
        "14711"
      ],
      [
        "55888.76",
        "11554"
      ],
      [
        "55888.92",
        "139716"
      ],
      [
        "55889.06",
        "88918"
      ],
      [
        "55889.2",
        "3856"
      ]
    ]
  },
  "ts": 1725624567033
}
```

