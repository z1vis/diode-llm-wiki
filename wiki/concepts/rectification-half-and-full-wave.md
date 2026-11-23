---
id: rectification-half-and-full-wave
title: "整流原理、半波與全波整流比較（含脈動頻率與濾波概念）"
type: concept
sources:
  - raw/S04_AAC_整流電路.md
  - raw/S02_AAC_二極體符號方向.md
status: ingested
last_updated: 2026-11-23
---

# 整流原理、半波與全波整流比較

## 一句話白話理解（給零基礎者）

牆壁插座來的是方向來回切換的交流電（AC）；**整流**就是利用二極體的單向閥門特性，讓流過負載的電流**永遠只朝同一個方向走**——半波整流把反方向那一半直接擋掉，全波整流則是把反方向那一半也「翻成同一方向」加以利用。

---

## 核心概念與電路意義

### 1. 什麼是整流（Rectification）？
- 利用二極體的方向性（參見 [diode-symbol-and-direction.md](./diode-symbol-and-direction.md)），把正負交替的交流輸入（AC）轉換為負載端**極性固定**的脈動輸出。

### 2. 半波整流 vs 全波整流比較

| 比較項目 | 半波整流（Half-Wave） | 全波整流（Full-Wave） |
| :--- | :--- | :--- |
| **利用的交流週期** | 僅利用輸入的**一個半週**（另一半週被阻擋、輸出近似為零） | 同時利用**正半週與負半週**，兩半週均於負載端形成同一極性 |
| **理想正弦輸入（頻率 `f`）之輸出脈動頻率** | **`f`**（每個交流週期出現 1 個脈動波峰） | **`2f`**（每個交流週期出現 2 個同向脈動波峰） |
| **波形特性** | 有明顯的零電壓空檔（半個週期無輸出） | 兩半週皆有輸出，脈動間隔減半、較利於後續濾波 |

### 3. 關鍵區分：「固定極性」不等於「平滑直流」
- **固定極性（脈動直流，Pulsating DC）**：電壓／電流始終維持單一方向（不再正負翻轉），但振幅依然會隨時間從 `0` 升到峰值再降回 `0`，這種殘留的上下起伏稱為**漣波（ripple）**。
- **平滑直流（Smooth DC）**：電壓幾乎不隨時間變動、無明顯漣波。
- **結論**：單靠整流電路**不會**得到完全無漣波的平滑直流；若後端電路需要穩定的平直直流電，還必須在整流之後加上**濾波（filtering）**（用濾波電路把波浪般的脈動起伏盡量撫平）。

---

## 相關頁面連結

- 上游觀念：[diode-symbol-and-direction.md](./diode-symbol-and-direction.md)、[diode-circuit-models.md](./diode-circuit-models.md)
- 核心實作電路：[bridge-rectifier.md](./bridge-rectifier.md)（四顆二極體全波橋式整流與 `2 V_F` 壓降）
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M6、M7、M8、M9）
- 來源摘要：[src-04-aac-rectifier-circuits.md](../sources/src-04-aac-rectifier-circuits.md)
- 返回總目錄：[index.md](../index.md)

---

## 來源溯源與已知限制

- **依據 `raw/` 檔案**：`raw/S04_AAC_整流電路.md`（中文改寫導讀筆記，非原文全文）
- **對應公開教材**：All About Circuits, *Rectifier Circuits*（https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/rectifier-circuits/）
- **已知限制**：橋式整流四顆二極體配置與 `2 V_F` 壓降已於 [bridge-rectifier.md](./bridge-rectifier.md) 補充；現有來源未包含濾波電容 RC 時間常數計算、中間抽頭變壓器全波比較或漣波量化公式。
