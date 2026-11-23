---
id: src-05-aac-bridge-rectifier
title: "來源 S05：All About Circuits Si Lab - Full-wave Bridge Rectifier（中文改寫導讀筆記）"
type: source
sources:
  - raw/S05_AAC_橋式整流器.md
status: ingested
last_updated: 2026-11-23
---

# 來源 S05：All About Circuits — Si Lab: Full-wave Bridge Rectifier

- **對應 `raw/` 檔案**：`raw/S05_AAC_橋式整流器.md`
- **素材性質（誠實標示）**：AI 輔助改寫之中文導讀筆記（paraphrased Chinese source note），**非**英文教材原文全文。
- **原始公開教材來源**：All About Circuits, *Si Lab - Full-wave Bridge Rectifier*  
  URL：https://www.allaboutcircuits.com/textbook/experiments/chpt-5/full-wave-bridge-rectifier/

---

## 擷取知識重點

1. **四顆二極體全波配置**：橋式整流器透過四顆二極體的橋式連接，讓交流電的正、負兩個半週在負載端都能維持**相同方向的電流**。
2. **每半週僅兩顆二極體導通**：在每個正常導通的半週中，完整電流迴路只經過**兩顆串聯的二極體**（另一對二極體截止），**並非**四顆二極體同時導通。
3. **簡化輸出電壓公式與兩倍壓降**：在**固定壓降模型（CVD）、純電阻負載、未加濾波**等簡化條件下，負載端瞬間輸出電壓約為：
   $$v_o(t) \approx \max\bigl(|v_s(t)| - 2 V_F,\; 0\bigr)$$
4. **教學核對關鍵**：因為每次電流皆穿過兩顆導通二極體，總正向壓降為 **`2 × V_F`**（非單顆 `V_F`），同時必須核對負載兩端極性與電流方向是否一致。

---

## 本次建立／更新之 Wiki 頁面

- 新增概念頁：[bridge-rectifier.md](../concepts/bridge-rectifier.md)
- 新增流程頁：[bridge-current-path-tracing.md](../procedures/bridge-current-path-tracing.md)
- 新增跨來源綜合頁：[curriculum-order.md](../curriculum-order.md)
- 更新概念／流程頁：[rectification-half-and-full-wave.md](../concepts/rectification-half-and-full-wave.md)、[diode-circuit-models.md](../concepts/diode-circuit-models.md)、[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)
- 更新迷思頁：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（新增誤區 M8、M9）
- 更新索引：[index.md](../index.md)

---

## 來源已知限制／未涵蓋處

- 導讀筆記未指定四顆二極體的具體編號命名（Wiki 內使用 `D1`～`D4` 係為標準教學編號慣例，用以清楚追蹤 S05 所述的兩組交替導通對）。
- 未涵蓋二極體反向峰值耐壓（PIV）規格選型、電容／電感性負載之波形計算，以及實際儀器（如示波器共地）接線限制。
