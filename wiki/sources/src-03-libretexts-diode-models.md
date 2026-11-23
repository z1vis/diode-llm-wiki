---
id: src-03-libretexts-diode-models
title: "來源 S03：Engineering LibreTexts 2.4 Diode Circuit Models（中文改寫導讀筆記）"
type: source
sources:
  - raw/S03_LibreTexts_二極體分析模型.md
status: ingested
last_updated: 2026-11-23
---

# 來源 S03：Engineering LibreTexts — 2.4 Diode Circuit Models

- **對應 `raw/` 檔案**：`raw/S03_LibreTexts_二極體分析模型.md`
- **素材性質（誠實標示）**：AI 輔助改寫之中文導讀筆記（paraphrased Chinese source note），**非**英文教材原文全文。
- **原始公開教材來源**：Engineering LibreTexts (Fiore), *Semiconductor Devices — Theory and Application*, Section 2.4 Diode Circuit Models  
  URL：https://eng.libretexts.org/Bookshelves/Electrical_Engineering/Electronics/Semiconductor_Devices_-_Theory_and_Application_%28Fiore%29/02%253A_PN_Junctions_and_Diodes/2.4%253A_Diode_Circuit_Models

---

## 擷取知識重點

1. **非線性與疊加原理限制**：二極體屬於非線性元件，因此二極體電路**不能**像純線性電阻網路一樣，在尚未確定導通狀態前直接套用疊加原理。
2. **三種常見簡化模型比較**：
   - **理想模型（Ideal Diode Model）**：把二極體視為方向受限的理想開關——導通（ON）時近似短路（`V_D = 0`），截止（OFF）時近似開路（`I_D = 0`）。
   - **固定壓降模型（Constant Voltage Drop, CVD Model）**：導通時加入近似正向壓降；矽二極體在入門電路分析中常以 `0.7 V` 近似。
   - **分段線性模型（Piecewise-Linear Model）**：進一步在固定壓降之外加上斜率（等效體電阻／動態電阻），更貼近真實特性；這說明**真實二極體並非在所有電流下都有固定壓降**。
3. **先假設再驗證法（Assume-and-Check）**：解二極體電路時，必須先假設各二極體為導通（ON）或截止（OFF），代入對應等效模型列式求解後，**回頭檢查算出的電流或電壓是否與原先假設一致**。
4. **來源檢核提醒**：`0.7 V` 是特定模型（固定壓降模型、矽二極體入門估算）中的**近似條件**，切勿表述為普遍不變的物理常數。

---

## 本次建立／更新之 Wiki 頁面

- 新增概念頁：[diode-circuit-models.md](../concepts/diode-circuit-models.md)
- 新增流程頁：[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)
- 更新概念頁：[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)、[diode-symbol-and-direction.md](../concepts/diode-symbol-and-direction.md)（建立模型與判斷流程交叉連結）
- 更新迷思頁：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（新增誤區 M4、M5）
- 更新索引：[index.md](../index.md)

---

## 來源已知限制／未涵蓋處

- 未提供分段線性模型之具體等效電阻數值（如 `r_B` / `r_d` 典型值）或完整 I-V 曲線圖數值。
- 未提供不同材料（如鍺、LED、蕭特基二極體）的典型壓降表。
- 導讀筆記僅給出「先假設再驗證」原則，並未內附具體數字例題（Wiki 流程頁若舉基本歐姆定律範例，將明確標示為「結合基礎歐姆定律與 S03 固定壓降模型之教學演算示意」）。
