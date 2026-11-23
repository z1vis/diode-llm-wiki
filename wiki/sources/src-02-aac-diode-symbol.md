---
id: src-02-aac-diode-symbol
title: "來源 S02：All About Circuits Introduction to Diodes and Rectifiers（中文改寫導讀筆記）"
type: source
sources:
  - raw/S02_AAC_二極體符號方向.md
status: ingested
last_updated: 2026-11-23
---

# 來源 S02：All About Circuits — Introduction to Diodes and Rectifiers

- **對應 `raw/` 檔案**：`raw/S02_AAC_二極體符號方向.md`
- **素材性質（誠實標示）**：AI 輔助改寫之中文導讀筆記（paraphrased Chinese source note），**非**英文教材原文全文。
- **原始公開教材來源**：All About Circuits, *Introduction to Diodes and Rectifiers*  
  URL：https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/introduction-to-diodes-and-rectifiers/

---

## 擷取知識重點

1. **單向導通與止回閥類比**：二極體相對容易讓電流沿特定單一方向流動，另一方向則顯著受阻，類似水管中的單向止回閥（check valve）。
2. **陽極 A 與陰極 K、傳統電流方向**：以**傳統電流方向（conventional current）**表示，正向電流經過二極體時係由**陽極 A（Anode）流向陰極 K（Cathode）**（`A → K`）。
3. **符號判讀與先標記習慣**：電路符號中，三角形頂端所抵住的**直線／橫線側對應陰極 K**；分析電路前應先在圖上標記出 `A` 與 `K` 端點。
4. **偏壓為相對端電位描述**：正向偏壓與反向偏壓係描述二極體兩端的**相對電位關係**，並不代表所有實際電路情況都能直接用理想開關精確表示。
5. **來源檢核提醒**：後續製作 HTML 簡報繪製二極體符號時，務必確認陰極橫線的位置與箭頭方向一致且正確。

---

## 本次建立／更新之 Wiki 頁面

- 新增概念頁：[diode-symbol-and-direction.md](../concepts/diode-symbol-and-direction.md)
- 更新概念頁：[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)（補充正／反偏為兩端相對電位關係，並建立與符號極性頁之雙向連結）
- 更新迷思頁：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（新增誤區 M3）
- 更新索引：[index.md](../index.md)

---

## 來源已知限制／未涵蓋處

- 未涵蓋實體零件外觀上的色環標記（如 1N400x 陰極銀環）或封裝極性識別細節。
- 未進一步區分不同簡化電路分析模型（理想模型、固定壓降模型、分段線性模型）與具體導通驗證步驟（預計由 S03 補充）。
