# Get information of currencies (available for deposit and withdraw) 

`GET` /v1/spot/public/wallet/support/currency

## Request Parameters

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/wallet/support/currency' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725588668232' \
--header 'validate-signature: e3346bcbfac04e7824f6f272f0adbf010152259d09c789a8f4ac0202ba78c098' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## Response Result

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": [
        {
            "currency": "btc",
            "supportChains": [
                {
                    "chain": "Bitcoin",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.0011,
                    "withdrawMinAmount": 0.00115,
                    "depositFeeRate": 0
                },
                {
                    "chain": "BNB Smart Chain",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.0011,
                    "withdrawMinAmount": 0.00115,
                    "depositFeeRate": 0
                },
                {
                    "chain": "Ethereum",
                    "depositEnabled": true,
                    "withdrawEnabled": false,
                    "withdrawFeeAmount": 0.00208,
                    "withdrawMinAmount": 0.00115,
                    "depositFeeRate": 0
                },
                {
                    "chain": "FIO",
                    "depositEnabled": false,
                    "withdrawEnabled": false,
                    "withdrawFeeAmount": 0.0006,
                    "withdrawMinAmount": 0.0005,
                    "depositFeeRate": 0
                }
            ]
        },
        {
            "currency": "eth",
            "supportChains": [
                {
                    "chain": "BNB Smart Chain",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.001,
                    "withdrawMinAmount": 0.001,
                    "depositFeeRate": 0
                },
                {
                    "chain": "Ethereum",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.000190,
                    "withdrawMinAmount": 0.000001,
                    "depositFeeRate": 0
                },
                {
                    "chain": "FIO",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.008,
                    "withdrawMinAmount": 0.01,
                    "depositFeeRate": 0
                },
                {
                    "chain": "ZkSync Era",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.00095,
                    "withdrawMinAmount": 0.0032,
                    "depositFeeRate": 0
                },
                {
                    "chain": "ARB",
                    "depositEnabled": true,
                    "withdrawEnabled": true,
                    "withdrawFeeAmount": 0.00001,
                    "withdrawMinAmount": 0.00001,
                    "depositFeeRate": 0
                }
            ]
        }
    ],
    "ts": 1725588668347
}

```

