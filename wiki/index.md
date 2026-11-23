# Wiki 總索引（Index）

> **知識庫主題**：二極體導通判斷與橋式整流器（面向無電子學基礎初學者）  
> **操作規則**：參見 [AGENTS.md](../AGENTS.md)  
> **實作日誌**：參見 [log.md](./log.md)  
> **目前狀態**：已完成 **5 / 5** 篇 Ingest（S01～S05）、三組實測 Query（Q1–Q3）、首次全庫 Lint 與 4 項修正，並已產出教學簡報 [outputs/index.html](../outputs/index.html)。

---

## 一、原始來源對照表（Sources）

> **素材性質聲明**：以下 5 份 `raw/` 檔案皆為附公開教材來源 URL 的**中文改寫導讀筆記（非原文全文）**，並保持唯讀不動。

| 編號 | 來源摘要頁 | 對應 `raw/` 檔案 | 原始公開教材 | 主要產出／更新 Wiki 頁面 | Ingest 狀態 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| S01 | [src-01-openstax-pn-junction.md](./sources/src-01-openstax-pn-junction.md) | `raw/S01_OpenStax_PN接面.md` | OpenStax — 9.7 Semiconductor Devices | `concepts/pn-junction-and-bias.md`, `misconceptions/...` (M1–M2) | **Done** |
| S02 | [src-02-aac-diode-symbol.md](./sources/src-02-aac-diode-symbol.md) | `raw/S02_AAC_二極體符號方向.md` | All About Circuits — Intro to Diodes and Rectifiers | `concepts/diode-symbol-and-direction.md`, 更新 `pn-junction-and-bias.md`, `misconceptions/...` (M3) | **Done** |
| S03 | [src-03-libretexts-diode-models.md](./sources/src-03-libretexts-diode-models.md) | `raw/S03_LibreTexts_二極體分析模型.md` | Engineering LibreTexts — 2.4 Diode Circuit Models | `concepts/diode-circuit-models.md`, `procedures/diode-conduction-assume-and-check.md`, `misconceptions/...` (M4–M5) | **Done** |
| S04 | [src-04-aac-rectifier-circuits.md](./sources/src-04-aac-rectifier-circuits.md) | `raw/S04_AAC_整流電路.md` | All About Circuits — Rectifier Circuits | `concepts/rectification-half-and-full-wave.md`, `misconceptions/...` (M6–M7) | **Done** |
| S05 | [src-05-aac-bridge-rectifier.md](./sources/src-05-aac-bridge-rectifier.md) | `raw/S05_AAC_橋式整流器.md` | All About Circuits — Si Lab: Full-wave Bridge Rectifier | `concepts/bridge-rectifier.md`, `procedures/bridge-current-path-tracing.md`, `curriculum-order.md`, `misconceptions/...` (M8–M9) | **Done** |

---

## 二、核心概念頁（Concepts）

- [pn-junction-and-bias.md](./concepts/pn-junction-and-bias.md) — PN 接面、空乏區、熱平衡（擴散與漂移相抵）及正／反向偏壓的物理與相對電位意義（來源：S01、S02）
- [diode-symbol-and-direction.md](./concepts/diode-symbol-and-direction.md) — 單向導通與止回閥類比、陽極 A／陰極 K 符號辨識、傳統電流 `A → K`（來源：S02）
- [diode-circuit-models.md](./concepts/diode-circuit-models.md) — 理想模型、固定壓降模型（矽 `0.7 V` 近似條件）、分段線性模型與非線性疊加限制（來源：S03，關聯 S01、S02、S05）
- [rectification-half-and-full-wave.md](./concepts/rectification-half-and-full-wave.md) — 整流目的、半波（`f`）vs 全波（`2f`）脈動頻率、固定極性脈動輸出不等於平滑 DC（來源：S04，關聯 S02、S05）
- [bridge-rectifier.md](./concepts/bridge-rectifier.md) — 橋式整流四顆配置、每半週兩顆導通對、負載同向電流與簡化壓降公式 `max(|v_s| − 2V_F, 0)`（來源：S05，關聯 S02～S04）

---

## 三、分析與判斷流程頁（Procedures）

- [diode-conduction-assume-and-check.md](./procedures/diode-conduction-assume-and-check.md) — 四步驟導通判斷 SOP：標記 A/K → 選模型與假設 → 列式求解 → 驗證假設是否矛盾（來源：S02、S03）
- [bridge-current-path-tracing.md](./procedures/bridge-current-path-tracing.md) — 橋式整流正／負半週電流路徑追蹤與雙重核對步驟（來源：S05，關聯 S02、S03）

---

## 四、常見錯誤與迷思（Misconceptions）

- [common-diode-and-rectifier-misconceptions.md](./misconceptions/common-diode-and-rectifier-misconceptions.md) — 彙整初學者 9 大常見誤區（M1～M9，跨 S01～S05）

---

## 五、跨來源綜合與查詢（Synthesis & Queries）

- [curriculum-order.md](./curriculum-order.md) — 整合 5 份來源的五階段零基礎教學順序與知識演化對照（來源：S01～S05）
- 實測紀錄與反思：[query-verification.md](../reports/query-verification.md)（Q1–Q3）、[lint-report.md](../reports/lint-report.md)、[workflow-reflection.md](../reports/workflow-reflection.md)
- 教學 HTML 簡報：[outputs/index.html](../outputs/index.html)
