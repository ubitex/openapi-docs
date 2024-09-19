# 查询近期成交列表

`GET` /v1/spot/public/trade/recent



## 请求参数

| 名称   | 位置  | 类型    | 必选 | 说明   |
| ------ | ----- | ------- | ---- | ------ |
| symbol | query | string  | 否   | 交易对 |
| limit  | query | integer | 否   | 数量   |

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/spot/public/trade/recent?symbol=btc_usdt&limit=2' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725521384599' \
--header 'validate-signature: 36822fe15326882cbe9ee4a7f75ac172bbe75314efe080a8b43c7c7160b4aa90' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' 
```

## 响应结果

```json
{
    "code": 0,
    "msg": "success",
    "msgInfo": [],
    "data": [
        {
            "i": 401904467641141568,
            "t": 1725523492113,
            "p": "57224.00",
            "q": "0.002530",
            "v": "144.77672",
            "b": false
        },
        {
            "i": 401904447382653248,
            "t": 1725523487302,
            "p": "57217.56",
            "q": "0.002220",
            "v": "127.0229832",
            "b": false
        }
    ],
    "ts": 1725523500310
}
```

