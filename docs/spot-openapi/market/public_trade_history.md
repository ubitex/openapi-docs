`GET` /v1/spot/public/trade/history



## 请求参数

| 名称      | 位置  | 类型    | 必选 | 说明                             |
| --------- | ----- | ------- | ---- | -------------------------------- |
| symbol    | query | string  | 否   | 交易对                           |
| direction | query | string  | 否   | 方向（PREV:上一页；NEXT:下一页） |
| fromId    | query | integer | 否   | 起始ID                           |
| limit     | query | integer | 否   | 数量                             |

### 请求示例

/v1/spot/public/trade/history?symbol=btc_usdt&direction=NEXT&fromId&limit=2



## 响应结果

|      |      |      |
| ---- | ---- | ---- |
|      |      |      |

### 返回示例

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": {
        "hasPrev": false,
        "hasNext": true,
        "items": [
            {
                "i": 401904210568055104,
                "t": 1725523430831,
                "p": "57212.01",
                "q": "0.001450",
                "v": "82.9574145",
                "b": true
            },
            {
                "i": 401904120491182400,
                "t": 1725523409356,
                "p": "57231.10",
                "q": "0.033930",
                "v": "1941.851223",
                "b": true
            }
        ]
    },
    "ts": 1725523439385
}
```

