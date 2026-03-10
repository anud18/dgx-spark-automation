# Benchmark 報告 — CNN / DailyMail — 新聞摘要

> CNN 與 Daily Mail 共 30 萬篇新聞文章的摘要任務。特性：長輸入、短輸出（Summarization）。

## 執行配置：10 個並發用戶，共執行 600 秒

### 摘要

本次 benchmark 以 **10 個並發用戶**持續執行 **600 秒**。
Dataset 中平均每個 prompt 含 **799 個 input token**，模型回覆平均 **1296 個 output token**。

- **TTFT（到第一個字的等待時間）**：平均 **525.8ms**（P95: 2009.4ms） — 用戶送出 prompt 後等多久才開始看到回覆
- **TPOT（每個 output token 的生成時間）**：平均 **80.6ms**（P95: 83.3ms） — 體感約 12 tok/s 的生成速度
- **ITL（Token 間延遲）**：平均 **80.3ms**（P95: 83.2ms）
- **E2E 延遲**：平均 **104.60s**（P95: 153.87s） — 從送出 prompt 到收到完整回覆的總時間
- **Token Throughput**：output **356.0 tok/s**，total **575.4 tok/s**
- **Request Throughput**：**0.273 req/s**
- **平均活躍用戶數**：**28.8** / 10

### 詳細指標

| 指標 | 平均 | P50 | P95 | P99 |
|:-----|-----:|----:|----:|----:|
| TTFT (ms) | 525.8 | 294.2 | 2009.4 | 2775.7 |
| TPOT (ms) | 80.6 | 81.0 | 83.3 | 84.5 |
| ITL (ms) | 80.3 | 80.9 | 83.2 | 84.1 |
| E2E Latency (s) | 104.602 | 102.039 | 153.873 | 173.457 |
| Output Throughput (tok/s) | 356.0 | 273.1 | 896.3 | 1630.0 |
| Total Throughput (tok/s) | 575.4 | 273.3 | 901.9 | 1681.9 |
| RPS (req/s) | 0.273 | 0.214 | 0.591 | 1.082 |
| Active Users | 28.8 | 32.0 | 32.0 | 32.0 |
| Avg Input Tokens | 799.2 | 783.0 | 1425.0 | 1771.0 |
| Avg Output Tokens | 1296.4 | 1264.0 | 1911.0 | 2117.0 |

