# Benchmark 報告 — ShareGPT — 一般對話

> 真實使用者與 AI 的對話紀錄（ShareGPT_Vicuna_unfiltered），涵蓋各種日常問答與指令場景。

## 執行配置：10 個並發用戶，共執行 600 秒

### 摘要

本次 benchmark 以 **10 個並發用戶**持續執行 **600 秒**。
Dataset 中平均每個 prompt 含 **30 個 input token**，模型回覆平均 **1312 個 output token**。

- **TTFT（到第一個字的等待時間）**：平均 **490.5ms**（P95: 2282.3ms） — 用戶送出 prompt 後等多久才開始看到回覆
- **TPOT（每個 output token 的生成時間）**：平均 **67.5ms**（P95: 71.5ms） — 體感約 15 tok/s 的生成速度
- **ITL（Token 間延遲）**：平均 **67.2ms**（P95: 71.5ms）
- **E2E 延遲**：平均 **88.66s**（P95: 227.74s） — 從送出 prompt 到收到完整回覆的總時間
- **Token Throughput**：output **434.4 tok/s**，total **444.3 tok/s**
- **Request Throughput**：**0.328 req/s**
- **平均活躍用戶數**：**29.3** / 10

### 詳細指標

| 指標 | 平均 | P50 | P95 | P99 |
|:-----|-----:|----:|----:|----:|
| TTFT (ms) | 490.5 | 150.9 | 2282.3 | 2283.2 |
| TPOT (ms) | 67.5 | 69.1 | 71.5 | 72.4 |
| ITL (ms) | 67.2 | 69.1 | 71.5 | 72.3 |
| E2E Latency (s) | 88.657 | 77.760 | 227.736 | 284.820 |
| Output Throughput (tok/s) | 434.4 | 330.7 | 1082.1 | 1954.3 |
| Total Throughput (tok/s) | 444.3 | 330.8 | 1087.6 | 2005.9 |
| RPS (req/s) | 0.328 | 0.231 | 0.819 | 1.227 |
| Active Users | 29.3 | 32.0 | 32.0 | 32.0 |
| Avg Input Tokens | 29.8 | 21.0 | 88.0 | 158.0 |
| Avg Output Tokens | 1312.2 | 1185.0 | 3446.0 | 4075.0 |

