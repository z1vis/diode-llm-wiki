---
id: diode-symbol-and-direction
title: "二極體符號、陽極／陰極與傳統電流方向"
type: concept
sources:
  - raw/S02_AAC_二極體符號方向.md
status: ingested
last_updated: 2026-11-23
---

# 二極體符號、陽極／陰極與傳統電流方向

## 一句話白話理解（給零基礎者）

二極體就像水管裡的「**單向止回閥**」：順著符號箭頭（從 **陽極 A** 指向 **陰極 K 橫線端**）推，水流較容易通過；反著推則會被閥門顯著擋住。

---

## 核心概念與電路意義

### 1. 單向導通特性與止回閥類比
- 二極體在某一個方向上相對容易導通電流，而在相反方向上會顯著阻擋電流。
- 初學者可先將其類比為單向止回閥，但須留意：**類比僅幫助建立直覺，實際二極體並非毫無壓降或完全零漏電流的完美機械開關**。

### 2. 電路符號與端點標記（陽極 A / 陰極 K）
```text
陽極 A（Anode） ───▶|─── 陰極 K（Cathode）
               三角形  橫線端
         正向傳統電流方向：A → K
```
- **陽極 A（Anode）**：三角形底部（寬邊）一側。
- **陰極 K（Cathode）**：三角形尖端頂住的**橫線／直線端**。
- **重要分析習慣**：看到任何二極體電路，**動筆計算前應先標記每一顆二極體的 `A` 與 `K` 端點**，避免方向看錯導致整個導通判斷翻盤。

### 3. 傳統電流方向（Conventional Current）
- 在標準電路分析中採用**傳統電流方向**（由高電位流向低電位）：二極體正向導通時，電流方向為 **`A → K`**（順著三角形箭頭所指方向）。

### 4. 正／反向偏壓是「相對電位」描述
- 判斷正向偏壓或反向偏壓，看的是二極體兩端 **`A` 與 `K` 之間的相對電位差**，而不是看單一端點是否接在正電源或地線。
- 即使處於正向偏壓描述下，也不表示所有真實電路都能單靠理想開關模型精確計算（不同簡化分析模型見 [diode-circuit-models.md](./diode-circuit-models.md)）。

---

## 相關頁面連結

- 前置物理背景：[pn-junction-and-bias.md](./pn-junction-and-bias.md)（了解為什麼 PN 接面會呈現正反偏差異）
- 後續模型與判斷：[diode-circuit-models.md](./diode-circuit-models.md)、[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)
- 整流電路應用：[rectification-half-and-full-wave.md](./rectification-half-and-full-wave.md)、[bridge-rectifier.md](./bridge-rectifier.md)
- 來源摘要：[src-02-aac-diode-symbol.md](../sources/src-02-aac-diode-symbol.md)
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M3：看反陰極線或只看單點電位不看相對電位）
- 返回總目錄：[index.md](../index.md)

---

## 來源溯源與已知限制

- **依據 `raw/` 檔案**：`raw/S02_AAC_二極體符號方向.md`（附公開教材 URL 之中文改寫導讀筆記，非原文全文）
- **對應公開教材**：All About Circuits, *Introduction to Diodes and Rectifiers*（https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/introduction-to-diodes-and-rectifiers/）
- **繪圖檢核備忘**：製作 HTML 簡報 SVG 圖形時，須逐一檢查每顆二極體陰極橫線端的位置是否正確對應 `K`。
- **目前知識邊界**：具體電路數學分析模型已由 `S03` 補充至 [diode-circuit-models.md](./diode-circuit-models.md)；現有來源未涵蓋實體元件封裝上的陰極色環外觀標示。
