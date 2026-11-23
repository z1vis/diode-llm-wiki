---
id: src-04-aac-rectifier-circuits
title: "來源 S04：All About Circuits Rectifier Circuits（中文改寫導讀筆記）"
type: source
sources:
  - raw/S04_AAC_整流電路.md
status: ingested
last_updated: 2026-11-23
---

# 來源 S04：All About Circuits — Rectifier Circuits

- **對應 `raw/` 檔案**：`raw/S04_AAC_整流電路.md`
- **素材性質（誠實標示）**：AI 輔助改寫之中文導讀筆記（paraphrased Chinese source note），**非**英文教材原文全文。
- **原始公開教材來源**：All About Circuits, *Rectifier Circuits*  
  URL：https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/rectifier-circuits/

---

## 擷取知識重點

1. **整流的目的與原理**：利用二極體的單向導通特性，將方向交替變化的**交流輸入（AC）**轉換為負載端**固定極性的脈動輸出（unidirectional pulsating output）**。
2. **半波整流（Half-Wave Rectification）**：只利用交流輸入的其中一個半週（另一半週被二極體阻擋截止）；對於頻率為 `f` 的理想正弦波輸入，輸出脈動重複頻率仍為 **`f`**。
3. **全波整流（Full-Wave Rectification）**：同時利用輸入的正半週與負半週，將兩個半週都在負載端形成同一極性；對於頻率為 `f` 的理想正弦波輸入，輸出脈動頻率為 **`2f`**。
4. **整流 ≠ 平滑直流（DC）**：整流輸出雖然極性固定，但電壓大小仍隨時間起伏（脈動／含漣波），並不等於完全平直無漣波的平滑 DC；若需要穩定平滑直流，還需外加**濾波（filtering）**。
5. **來源檢核提醒**：後續製作 HTML 簡報時，務必明確區分「**固定極性**（方向不反轉）」與「**輸出不隨時間變動**（平滑恆定直流）」。

---

## 本次建立／更新之 Wiki 頁面

- 新增概念頁：[rectification-half-and-full-wave.md](../concepts/rectification-half-and-full-wave.md)
- 更新概念頁：[diode-symbol-and-direction.md](../concepts/diode-symbol-and-direction.md)、[diode-circuit-models.md](../concepts/diode-circuit-models.md)（建立整流應用交叉連結）
- 更新迷思頁：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（新增誤區 M6、M7）
- 更新索引：[index.md](../index.md)

---

## 來源已知限制／未涵蓋處

- 未提供中間抽頭變壓器式全波整流（center-tapped full-wave）與橋式整流的具體電路差異（橋式整流細節預計由 S05 補齊）。
- 未提供濾波電容容量計算、漣波電壓公式（`V_r`）或平均直流電壓積分推導（`V_dc`）。
