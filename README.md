# ETH AI 行情分析台（零预算起步版）

这是一个纯静态网页原型：不需要 API Key、不需要付费 AI API、不需要自购服务器。
行情来自 Coinbase Exchange 公共 API；RSI、EMA、MACD 和局部高低点支撑阻力由浏览器本地计算。

## 当前能做什么
- 显示 ETH-USD 最新公开报价、24小时涨跌和高低区间
- 获取 1 小时 K 线并计算 RSI(14)、EMA(20/50/200)、MACD
- 根据近期局部高低点估算动态支撑和阻力
- 显示趋势观察、情景分析和简单条件提醒
- 网页打开期间每 30 秒刷新

## 当前限制
- 关闭网页后不会继续监控
- 不会自动发送 Telegram 消息
- 没有调用大语言模型；分析文字由规则生成
- 公共 API 可能限流、延迟或在部分网络环境不可用
- 指标不是投资建议，也不保证预测准确

## 本地打开
解压后直接双击 `index.html`。如果浏览器限制本地请求，可在该目录运行：
`python -m http.server 8000`
然后打开 `http://localhost:8000`。

## 免费发布到网页
1. 登录 GitHub，创建一个新的 **Public** repository，例如 `eth-market-agent`。
2. 上传 `index.html` 和 `README.md`。
3. 进入仓库 Settings → Pages。
4. 在 Build and deployment 中选择 Deploy from a branch。
5. Branch 选择 `main`，目录选择 `/ (root)`，保存。
6. 等待 GitHub Pages 发布完成，打开页面显示的站点地址。

GitHub Pages 免费托管静态网页，但不是后台服务器；网页必须打开才会持续刷新。
