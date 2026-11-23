---
id: bridge-current-path-tracing
title: "橋式整流器正／負半週電流路徑追蹤步驟"
type: procedure
sources:
  - raw/S05_AAC_橋式整流器.md
  - raw/S02_AAC_二極體符號方向.md
  - raw/S03_LibreTexts_二極體分析模型.md
status: ingested
last_updated: 2026-11-23
---

# 橋式整流器正／負半週電流路徑追蹤步驟

## 一句話白話理解（給零基礎者）

不要死背哪兩顆導通！只要依序「**認清當下哪端電位高 → 沿著箭頭找進負載的路 → 穿過負載 → 再沿著箭頭找回低電位端**」，就能在 10 秒內自己推出每個半週的導通路徑並驗證負載極性。

---

## 四步驟追蹤法（結合 S02、S03、S05）

### 步驟 1：標出四顆二極體的 A／K 與負載兩端
- 依 [diode-symbol-and-direction.md](../concepts/diode-symbol-and-direction.md)，先在圖上標明 `D1`～`D4` 各自的陽極 `A` 與陰極 `K`（橫線側）。
- 標示兩顆陰極相連的節點為 `V_out+`（電流匯入負載端），兩顆陽極相連的節點為 `V_out−`（電流流出負載端）。

### 步驟 2：鎖定目前半週的高電位與低電位輸入端
- **正半週**：`AC+` 為高電位端，`AC−` 為低電位端。
- **負半週**：`AC−` 為高電位端，`AC+` 為低電位端。

### 步驟 3：依傳統電流方向（`A → K`）追蹤完整閉合迴路
- **正半週路徑**（需 `|v_s| > 2 V_F`）：
  1. 從高電位 `AC+` 出發，只有 `D1` 呈現順向（`A` 接 `AC+`），故經 **`D1`** 到 `V_out+`（`D4` 的 `K` 接 `AC+`，被反向阻擋）。
  2. 電流由 `V_out+` 穿過負載 **`R_L`** 流向 `V_out−`（因 `D3` 的 `K` 亦接 `V_out+` 且 `AC−` 電位低，故 `D3` 截止，電流不會走 `D3`）。
  3. 離開 `V_out−` 後，經順向的 **`D2`** 回到低電位端 `AC−`。
- **負半週路徑**（需 `|v_s| > 2 V_F`）：
  1. 從高電位 `AC−` 出發，只有 `D3` 呈現順向，故經 **`D3`** 到 `V_out+`（`D2` 反向阻擋）。
  2. 電流同樣由 `V_out+` 穿過負載 **`R_L`** 流向 `V_out−`（`D1` 反向阻擋）。
  3. 離開 `V_out−` 後，經順向的 **`D4`** 回到低電位端 `AC+`。

### 步驟 4：雙重核對（公式＋極性／方向）
1. **導通顆數核對**：任一導通半週皆剛好經過 **2 顆**串聯二極體（正半週 `D1, D2`；負半週 `D3, D4`），其餘 2 顆為反向偏壓截止。
2. **負載方向核對**：兩半週流過負載 `R_L` 的方向必須皆為 **`V_out+ → V_out−`**。
3. **壓降與模型核對**：在 CVD 模型、純電阻負載、無濾波下，檢核輸出電壓是否扣除 **`2 × V_F`**，即 `v_o ≈ max(|v_s| − 2 V_F, 0)`；若 `|v_s| ≤ 2 V_F`，四顆皆截止，輸出近似 `0 V`。

---

## 相關頁面連結

- 核心概念：[bridge-rectifier.md](../concepts/bridge-rectifier.md)
- 通用假設驗證 SOP：[diode-conduction-assume-and-check.md](./diode-conduction-assume-and-check.md)
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M8、M9）
- 來源摘要：[src-05-aac-bridge-rectifier.md](../sources/src-05-aac-bridge-rectifier.md)
- 返回總目錄：[index.md](../index.md)
