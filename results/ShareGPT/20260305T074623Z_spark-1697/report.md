# Benchmark 報告 — ShareGPT — 一般對話

> 真實使用者與 AI 的對話紀錄（ShareGPT_Vicuna_unfiltered），涵蓋各種日常問答與指令場景。

## 執行配置：10 個並發用戶，共執行 60 秒

### 摘要

本次 benchmark 以 **10 個並發用戶**持續執行 **60 秒**。
Dataset 中平均每個 prompt 含 **20 個 input token**，模型回覆平均 **519 個 output token**。

- **TTFT（到第一個字的等待時間）**：平均 **72.6ms**（P95: 82.4ms） — 用戶送出 prompt 後等多久才開始看到回覆
- **TPOT（每個 output token 的生成時間）**：平均 **27.0ms**（P95: 27.9ms） — 體感約 37 tok/s 的生成速度
- **ITL（Token 間延遲）**：平均 **26.9ms**（P95: 27.7ms）
- **E2E 延遲**：平均 **14.05s**（P95: 32.86s） — 從送出 prompt 到收到完整回覆的總時間
- **Token Throughput**：output **289.5 tok/s**，total **300.4 tok/s**
- **Request Throughput**：**0.550 req/s**
- **平均活躍用戶數**：**7.9** / 10

### 詳細指標

| 指標 | 平均 | P50 | P95 | P99 |
|:-----|-----:|----:|----:|----:|
| TTFT (ms) | 72.6 | 77.3 | 82.4 | 82.9 |
| TPOT (ms) | 27.0 | 27.4 | 27.9 | 27.9 |
| ITL (ms) | 26.9 | 27.3 | 27.7 | 27.9 |
| E2E Latency (s) | 14.049 | 13.778 | 32.865 | 40.161 |
| Output Throughput (tok/s) | 289.5 | 226.3 | 719.9 | 1306.5 |
| Total Throughput (tok/s) | 300.4 | 226.5 | 729.8 | 1393.8 |
| RPS (req/s) | 0.550 | 0.473 | 1.030 | 2.744 |
| Active Users | 7.9 | 10.0 | 10.0 | 10.0 |
| Avg Input Tokens | 19.5 | 18.0 | 42.0 | 44.0 |
| Avg Output Tokens | 519.3 | 533.0 | 1194.0 | 1448.0 |

### 與前次執行比較（20260305T073746Z_spark-1697）

> v = 改善（數值下降），^ = 退步（數值上升），- = 持平

| 指標 | 本次 | 前次 | 變化 |
|:-----|-----:|-----:|:-----|
| TTFT (ms) | 72.58ms | 127.37ms | v -43.0% |
| TPOT (ms) | 27.00ms | 43.05ms | v -37.3% |
| ITL (ms) | 26.91ms | 42.92ms | v -37.3% |
| E2E Latency (s) | 14.05s | 27.38s | v -48.7% |
| Output Throughput (t/s) | 289.52 | 645.02 | ^ -55.1% |
| RPS (req/s) | 0.55 | 1.01 | ^ -45.7% |

