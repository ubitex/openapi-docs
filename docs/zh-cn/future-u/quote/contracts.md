获取合约信息

`GET` /v1/future-u/market/public/cg/contracts

## 请求参数

注：此方法不需要签名

> 请求示例

```shell
curl --location --request GET 'https://api.ubitex.com/v1/future-u/market/public/cg/contracts' \
--header 'Accept: */*' \
--header 'Host: api.ubitex.com' \
--header 'Connection: keep-alive'
```

## 响应结果

```json
[
  {
    "id": 123,
    "ask": "1817.32",
    //当前最低价
    "base_currency": "ETH",
    //标的币种，比如 BTC
    "base_volume": "13267684284",
    //24小时交易量
    "bid": "1817.31",
    //当前最高价
    "contractSize": 10,
    //合约面值
    "end_timestamp": 253402099200000,
    //该衍生品的终结时间
    "funding_rate": "-0.03",
    //资金费率
    "high": "1828.89",
    //24小时最高成交价
    "index_currency": "USD",
    //指数的基础币种
    "index_name": "ETH-USD",
    //基础指数的名称
    "index_price": "1816.61",
    //基础指数价格
    "last_price": "1817.31",
    //最新价格
    "low": "1778.65",
    //24小时最低成交价
    "next_funding_rate": "-0.03",
    //预计下一个资金费率
    "next_funding_rate_timestamp": 1698681600000,
    //下一个资金费率时间
    "open_interest": "2419347630",
    //24小时合约持仓量
    "product_type": "PERPETUAL",
    //产品类型
    "start_timestamp": 1651328033000,
    //该衍生品的开始时间
    "symbol": "eth_usd",
    "target_currency": "USD",
    //报价币种
    "target_volume": "73698647.51054371",
    //24小时交易量
    "ticker_id": "ETH-USD",
    //代码标识符
    "underlyingType": 1
    //标的类型，币本位，u本位
  }
]
```

