# Get currency transfer network information

`GET` /v1/spot/public/currency/{currencyId}

## Request Parameters

> Request Example

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/currency/11' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 60000' \
--header 'validate-timestamp: 1725611186697' \
--header 'validate-signature: 0eaf0c2fc04de7d4b31a3e3977957e250d1c20d2671b1b801ee76874f556fe68' \
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
            "id": 1927,
            "currencyId": 11,
            "currency": "usdt",
            "chainId": 1664,
            "chain": "ARB",
            "protocol": "",
            "weight": 1000,
            "isNeedMemo": 0,
            "confirmations": 12,
            "depositMinAmount": "0",
            "withdrawMinAmount": "0.01",
            "withdrawPrecision": 2,
            "depositStatus": 1,
            "withdrawStatus": 1,
            "relationDepositStatus": 1,
            "relationWithdrawStatus": 1,
            "contract": "0xFd086bC7CD5C481DCC9C85ebE478A1C0b69FCbb9",
            "supportDepositSpeed": 0,
            "tradeLink": "https://arbiscan.io/tx/",
            "blockLink": "https://arbiscan.io/address/"
        },
        {
            "id": 265,
            "currencyId": 11,
            "currency": "usdt",
            "chainId": 715,
            "chain": "BNB Smart Chain",
            "protocol": "BEP20",
            "weight": 1000,
            "isNeedMemo": 0,
            "confirmations": 3,
            "depositMinAmount": "0.00001",
            "withdrawMinAmount": "0.00001",
            "withdrawPrecision": 8,
            "depositStatus": 1,
            "withdrawStatus": 1,
            "relationDepositStatus": 1,
            "relationWithdrawStatus": 1,
            "contract": "0x55d398326f99059ff775485246999027b3197955",
            "supportDepositSpeed": 0,
            "tradeLink": "https://bscscan.com/tx/",
            "blockLink": "https://bscscan.com/address/"
        },
        {
            "id": 22,
            "currencyId": 11,
            "currency": "usdt",
            "chainId": 73,
            "chain": "Tron",
            "protocol": null,
            "weight": 9,
            "isNeedMemo": 0,
            "confirmations": 6,
            "depositMinAmount": "0.1",
            "withdrawMinAmount": "10",
            "withdrawPrecision": 6,
            "depositStatus": 1,
            "withdrawStatus": 1,
            "relationDepositStatus": 1,
            "relationWithdrawStatus": 1,
            "contract": "TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t",
            "supportDepositSpeed": 0,
            "tradeLink": "https://tronscan.io/#/transaction/",
            "blockLink": "https://tronscan.io/#/address/"
        }
    ],
    "ts": 1725611187115
}
```

