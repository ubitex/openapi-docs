# Cancel the current pending order

`DELETE` /v1/spot/open-order

## Request Parameters

| name      | location   | type     | required | Description                      |
|---------|------|--------|----|-------------------------|
| symbol  | body | string | Yes  | symbol，不传代表所有	             |
| bizType | body | string | Yes  | 业务type SPOT-现货	 |
| side    | body | string | Yes  | BUY-买,SELL-卖	           |
| mode    | body | string | Yes  | 模式：CMD-命令式,ITERATOR-迭代式 |

> Request Example

```shell
curl --location --request DELETE 'https://api.ubitex.com/v1/spot/open-order' \
--header 'Content-Type: application/json' \
--header 'validate-algorithms: HmacSHA256' \
--header 'validate-appkey: 2fa91add-388c-44f2-8365-f4b72886c135' \
--header 'validate-recvwindow: 6000' \
--header 'validate-timestamp: 1725547790951' \
--header 'validate-signature: ad9489ea14dee72963a45c3ab1e724dd049cec298fb6418d166b00d70b6cab9a' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive' \
--header 'Cookie: JSESSIONID=8FF5A9153450BDA558BF120CD75F0632' \
--data-raw '{"symbol":"btc_usdt","side":"SELL","bizType":"SPOT","mode":"CMD"}'
```

## Response Result

```json
{
  "code": 0,
  "msg": "success",
  "msgInfo": [],
  "data": null,
  "ts": 1724923978773
}
```

