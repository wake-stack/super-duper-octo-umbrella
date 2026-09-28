# 数据契约（待阶段 1A 确定）

## 先记录数据源

- 提供方、接口与授权范围：
- 股票代码格式与交易所：
- 交易日历和时区：Asia/Shanghai
- 日线复权方式：未复权 / 前复权 / 后复权；不得混用
- 更新时点、历史修订与增量边界：
- 限频、失败重试和缺失数据处理：

## 建议日线字段

`symbol`, `trade_date`, `open`, `high`, `low`, `close`, `volume`, `amount`, `adjustment`, `source`, `fetched_at`。

价格、成交量和成交额的单位必须按具体数据源核对；主键建议为 `(symbol, trade_date, adjustment)`。存储原始响应或可追溯标识，以便核查供应商历史修订。报表和新闻保留“实际可见时间”，供回测防止未来函数。
