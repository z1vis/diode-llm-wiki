---
id: diode-conduction-assume-and-check
title: "二極體導通判斷標準步驟（先標記、再假設、列式、最後驗證）"
type: procedure
sources:
  - raw/S02_AAC_二極體符號方向.md
  - raw/S03_LibreTexts_二極體分析模型.md
status: ingested
last_updated: 2026-11-23
---

# 二極體導通判斷標準步驟（Assume-and-Check）

## 一句話白話理解（給零基礎者）

判斷二極體到底有沒有導通，**不能光靠肉眼硬猜**——先標清楚箭頭方向，大膽「先假設它導通（或截止）」，用基礎歐姆定律算完後再「回頭驗算假設合不合理」；合理就定案，矛盾就換個假設重算。

---

## 四步驟標準操作流程（SOP）

### 步驟 1：先標記端點與正向電流方向（依據 S02）
- 在電路圖上標出每顆二極體的**陽極 `A`**（三角形底邊）與**陰極 `K`**（橫線側）。
- 標出傳統正向電流參考方向：`I_D` 由 **`A → K`**，跨壓 `V_D = V_A − V_K`。

### 步驟 2：選定分析模型並「假設」導通狀態（依據 S03）
- 決定使用的簡化模型（例如初學者常用的**理想模型**，或矽二極體常用的**固定壓降模型 CVD，`V_F ≈ 0.7 V`**）。
- 針對每顆二極體先假設狀態：
  - 若假設 **導通（ON）**：理想模型以**短路（`V_D = 0`）**取代；CVD 模型以**固定正向壓降（`V_D ≈ 0.7 V`，A 正 K 負）**取代。
  - 若假設 **截止（OFF）**：以**開路（`I_D = 0`）**取代。

### 步驟 3：列式求解電路（依據 S03 ＋ 先備歐姆定律／KVL／KCL）
- 由於二極體已被替換為線性等效元件（短路、定壓降源或開路），此時即可用歐姆定律，搭配兩項基礎電路守恆法則求解未知的 `I_D`（當假設 ON）或 `V_D`（當假設 OFF）：
  - **KVL（克希荷夫電壓定律）**：沿著任何封閉迴路繞一圈，電源提供的電壓總和等於各元件消耗的壓降總和。
  - **KCL（克希荷夫電流定律）**：在任何電路交會點（節點），流入的總電流等於流出的總電流。

### 步驟 4：檢查結果是否與假設相符（關鍵驗證關卡，依據 S03）
- **若原本假設 ON（導通）**：檢查算出的正向電流 `I_D`（`A → K` 方向）是否為正向導通（`I_D > 0`；若剛好 `I_D = 0` 則位於導通／截止臨界邊界）。
  - 符合 → **假設成立**，此解有效。
  - 不符合（算出負電流 `I_D < 0`，代表電流企圖倒流）→ **假設矛盾**，改假設 OFF 重新計算。
- **若原本假設 OFF（截止）**：檢查算出的開路端跨壓 `V_D = V_A − V_K` 是否未超過導通門檻（理想模型下 `V_D ≤ 0`；CVD 模型下 `V_D ≤ V_F`，例如矽二極體近似 `≤ 0.7 V`，等號處為臨界點且 `I_D = 0`，與橋式整流 `|v_s| ≤ 2 V_F` 截止條件一致）。
  - 符合 → **假設成立**，二極體確實截止。
  - 不符合（開路跨壓高於門檻，例如 CVD 模型下 `V_D > 0.7 V`）→ **假設矛盾**，改假設 ON 重新計算。

---

## 教學演算示意（結合先備歐姆定律與 S03 固定壓降模型）

> **透明標註**：`raw/S03_LibreTexts_二極體分析模型.md` 提供模型定義與假設驗證原則，並未內含以下具體數字；此處係結合初學者先備知識（歐姆定律／KVL）與 S03 矽二極體 CVD 模型（`V_F ≈ 0.7 V`）所作的教學示範。

- **情境 A（可導通）**：`5 V` 直流電源串聯 `1 kΩ` 電阻與一顆順向連接的矽二極體（假設 ON，採 CVD 模型 `V_F ≈ 0.7 V`）：
  1. 列式：`I_D = (5 V − 0.7 V) / 1000 Ω = 4.3 mA`。
  2. 驗證：`I_D = 4.3 mA > 0`，方向符合 `A → K`，故 **ON 假設成立**。
- **情境 B（電源不足以跨越近似門檻）**：若將電源改為 `0.4 V`，同樣假設 ON（CVD 模型 `V_F ≈ 0.7 V`）：
  1. 列式：`I_D = (0.4 V − 0.7 V) / 1000 Ω = −0.3 mA`。
  2. 驗證：`I_D < 0`（與正向導通假設矛盾！）→ **推翻 ON 假設**，改假設 OFF（開路，`I_D = 0`），此時開路跨壓 `V_D = 0.4 V < 0.7 V`，**OFF 假設成立**。

---

## 相關頁面連結

- 前置觀念：[diode-symbol-and-direction.md](../concepts/diode-symbol-and-direction.md)、[diode-circuit-models.md](../concepts/diode-circuit-models.md)
- 進階多二極體應用：[bridge-current-path-tracing.md](./bridge-current-path-tracing.md)、[bridge-rectifier.md](../concepts/bridge-rectifier.md)
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M3、M4、M5）
- 來源摘要：[src-02-aac-diode-symbol.md](../sources/src-02-aac-diode-symbol.md)、[src-03-libretexts-diode-models.md](../sources/src-03-libretexts-diode-models.md)
- 返回總目錄：[index.md](../index.md)
