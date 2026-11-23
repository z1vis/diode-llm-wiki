---
id: diode-circuit-models
title: "二極體電路分析模型（理想／固定壓降／分段線性）"
type: concept
sources:
  - raw/S03_LibreTexts_二極體分析模型.md
  - raw/S01_OpenStax_PN接面.md
  - raw/S02_AAC_二極體符號方向.md
status: ingested
last_updated: 2026-11-23
---

# 二極體電路分析模型（理想／固定壓降／分段線性）

## 一句話白話理解（給零基礎者）

真實二極體的電壓與電流關係是非線性的，直接算太複雜；工程師會依照需要的精確度，改用三種「**漸進式簡化替身（模型）**」來估算電路——從最粗略的「單向開關（理想模型）」，到入門最常用的「扣除約 `0.7 V` 門票（固定壓降模型）」，再到更精細的「門票＋斜率電阻（分段線性模型）」。

---

## 核心概念與電路意義

### 1. 為什麼二極體電路不能直接套用疊加原理？
- 純電阻電路是線性的，可用**疊加原理**（把多個電源拆開單獨計算、最後再把結果相加的線性電路技巧）；但二極體的導通與否取決於跨壓與電流方向，屬於**非線性元件**。
- 因此在**尚未確定二極體的導通狀態之前**，不可直接像線性電阻網路那樣套用疊加原理，而須先選定簡化模型並搭配[先假設再驗證法](../procedures/diode-conduction-assume-and-check.md)。

### 2. 三種常用簡化模型比較

> **名詞白話小抄**：**短路**＝如同接上一條無阻礙的理想導線，兩端壓降視為 `0 V`；**開路**＝如同把開關切斷、電路斷開，電流為 `0 A`。

| 模型名稱 | 導通（ON）時等效 | 截止（OFF）時等效 | 適用場景與限制 |
| :--- | :--- | :--- | :--- |
| **理想模型（Ideal Diode Model）** | 近似**短路**（導通壓降視為 `0 V`） | 近似**開路**（電流視為 `0 A`） | 適合快速定性判斷方向，或電源電壓遠大於二極體壓降時的粗估；忽略實際正向壓降與漏電流。 |
| **固定壓降模型（Constant Voltage Drop, CVD）** | 近似一個固定正向壓降（矽二極體入門分析常取 **`V_F ≈ 0.7 V`**） | 近似**開路**（電流視為 `0 A`） | 入門電路計算與橋式整流壓降估算最常用。**注意：`0.7 V` 僅為此模型下矽二極體的近似條件，並非所有元件與電流下皆固定不變的物理常數。** |
| **分段線性模型（Piecewise-Linear Model）** | 固定壓降串聯一段**斜率／等效電阻** | 近似**開路** | 比 CVD 更貼近真實特性，反映出「電流愈大、實際壓降會隨之略有上升」的現象。 |

### 3. 特別強調：如何正確理解「0.7 V」
- 結合 S01 與 S03 的知識演化：
  - **物理事實（S01）**：正向偏壓降低 PN 接面障礙，並非超過 `0.7 V` 就瞬間產生固定電流。
  - **電路近似（S03）**：`0.7 V` 是在**矽二極體的固定壓降模型（CVD）**中為了方便入門分析所選用的近似正向壓降；真實二極體並非在所有電流下都有完全固定的壓降。

---

## 相關頁面連結

- 上游物理與符號：[pn-junction-and-bias.md](./pn-junction-and-bias.md)、[diode-symbol-and-direction.md](./diode-symbol-and-direction.md)
- 操作步驟 SOP：[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)
- 整流應用延伸：[rectification-half-and-full-wave.md](./rectification-half-and-full-wave.md)、[bridge-rectifier.md](./bridge-rectifier.md)（CVD 模型應用於橋式整流 `2 V_F` 壓降估算）
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M1、M4、M5）
- 來源摘要：[src-03-libretexts-diode-models.md](../sources/src-03-libretexts-diode-models.md)
- 返回總目錄：[index.md](../index.md)

---

## 來源溯源與已知限制

- **主要依據 `raw/` 檔案**：`raw/S03_LibreTexts_二極體分析模型.md`（中文改寫導讀筆記，非原文全文）；交叉關聯 `raw/S01_OpenStax_PN接面.md`、`raw/S02_AAC_二極體符號方向.md`。
- **對應公開教材**：Engineering LibreTexts (Fiore), *2.4 Diode Circuit Models*（https://eng.libretexts.org/Bookshelves/Electrical_Engineering/Electronics/Semiconductor_Devices_-_Theory_and_Application_%28Fiore%29/02%253A_PN_Junctions_and_Diodes/2.4%253A_Diode_Circuit_Models）
- **已知限制**：現有來源未提供分段線性模型之具體電阻數值、指數型 Shockley 方程式，亦未列出鍺／蕭特基／發光二極體（LED）之數值對照表。
