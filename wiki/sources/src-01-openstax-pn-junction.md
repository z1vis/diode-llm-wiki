---
id: src-01-openstax-pn-junction
title: "來源 S01：OpenStax 9.7 Semiconductor Devices（中文改寫導讀筆記）"
type: source
sources:
  - raw/S01_OpenStax_PN接面.md
status: ingested
last_updated: 2026-11-23
---

# 來源 S01：OpenStax 9.7 Semiconductor Devices

- **對應 `raw/` 檔案**：`raw/S01_OpenStax_PN接面.md`
- **素材性質（誠實標示）**：AI 輔助改寫之中文導讀筆記（paraphrased Chinese source note），**非**英文教材原文全文。
- **原始公開教材來源**：OpenStax, *University Physics Volume 3*, Section 9.7 Semiconductor Devices  
  URL：https://openstax.org/books/university-physics-volume-3/pages/9-7-semiconductor-devices

---

## 擷取知識重點

1. **PN 接面與空乏區形成**：當 P 型與 N 型半導體接觸時，載子擴散與內建電場相互作用，在交界處形成**空乏區（depletion region）**。
2. **熱平衡的動態本質**：未外加電壓達到熱平衡時，擴散作用與漂移作用產生的淨電流互相抵銷（淨電流為零），但這**不代表**擴散與漂移已停止。
3. **正向偏壓（Forward Bias）**：外加正向偏壓會降低載子跨越接面的障礙，使電流較容易通過。
4. **反向偏壓（Reverse Bias）**：外加反向偏壓一般會抑制多數載子跨越接面，但實際上仍存在少量反向電流（並非絕對零電流）。
5. **來源檢核提醒**：不應把正向導通簡化為「電壓一超過 `0.7 V` 就會瞬間出現固定電流」。

---

## 本次建立／更新之 Wiki 頁面

- 新增概念頁：[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)
- 新增迷思頁：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（新增誤區 M1、M2）
- 更新索引：[index.md](../index.md)

---

## 來源已知限制／未涵蓋處

- 未提供指數型二極體電流方程式（Shockley equation）之量化推導。
- 未提供不同半導體材料（如矽 vs 鍺、蕭特基二極體）之內建電位數值比較。
- 未涵蓋反向崩潰電壓（breakdown / PIV）之量化規格。
- 尚未說明二極體電路符號與陽極／陰極標記（預計由後續 S02 補充）。
