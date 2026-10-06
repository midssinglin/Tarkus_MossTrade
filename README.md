# MOSSTRADE｜循著訊號，讀懂市場

多市場交易分析網站（FastAPI + Lightweight Charts）。支援 OKX 永續合約／現貨、台股、美股與貴金屬 ETF 的 K 線、技術指標（EMA、ATR、布林通道、斐波那契、CHoCH、FVG）、多因子訊號評分、排行榜與模擬交易。

> 本站行情、技術指標、策略分析及模擬交易僅供學習與研究參考，不構成投資建議。

## 本機執行

```bash
pip install -r requirements.txt
uvicorn main:app --host 0.0.0.0 --port 8000
```

開啟 http://localhost:8000

## 主要 API

| 路徑 | 說明 |
|---|---|
| `/api/analyze?symbol=OKX:BTC-USDT-SWAP&interval=1h` | K 線、指標與多因子訊號 |
| `/api/search?keyword=2330` | 商品搜尋 |
| `/api/market-ranking?market=futures&ranking=gainers` | 排行榜（futures／taiwan／us／metals） |
| `/api/sim/spec?symbol=...` | 模擬交易商品規格 |

## 資料來源

OKX 公開 API、Yahoo Finance、Nasdaq、臺灣證券交易所／櫃買中心 OpenAPI。

## 部署

- Render：見 `render.yaml`
- AWS EC2：Amazon Linux 2023 + Python 3.11，以 systemd 執行 `uvicorn main:app --host 0.0.0.0 --port 80`
