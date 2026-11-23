---
id: pn-junction-and-bias
title: "PN 接面、空乏區與正／反向偏壓"
type: concept
sources:
  - raw/S01_OpenStax_PN接面.md
  - raw/S02_AAC_二極體符號方向.md
status: ingested
last_updated: 2026-11-23
---

# PN 接面、空乏區與正／反向偏壓

## 一句話白話理解（給零基礎者）

把兩種不同特性的半導體（P 型與 N 型）接在一起，交界處會自然長出一道「緩衝門檻（空乏區）」；**順著方向推（正向偏壓）會把門檻壓低**讓電流容易過，**反著方向拉（反向偏壓）則會擋住大多數電流**。

---

## 核心概念與物理意義

### 1. PN 接面與空乏區（Depletion Region）
- 當 **P 型半導體** 與 **N 型半導體** 接觸形成 **PN 接面（PN junction）** 時，兩側的**載子**（半導體內負責傳遞電荷的微小粒子，例如帶負電的電子與帶正電的電洞）會因濃度差異而產生**擴散（diffusion）**（像墨水滴進清水般，從濃度高的一側自然往低處散開）。
- 載子擴散在交界附近建立起**內建電場**，進而形成一段缺乏自由載子的區域，稱為**空乏區**。

### 2. 熱平衡並非靜止不動
- 在沒有外加電源的**熱平衡**狀態下，由濃度差驅動的**擴散電流**與由內建電場驅動的**漂移（drift）電流**（載子受電場推拉而產生的定向移動）大小相等、方向相反，因此**淨電流為零**。
- 關鍵觀念：淨電流相抵不代表擴散與漂移兩種物理作用不存在，而是處於動態平衡。

### 3. 正向偏壓（Forward Bias）
- 外加正向偏壓會**降低**載子跨越 PN 接面的障礙，有利於電流通過二極體。
- **重要提醒**：正向導通是一個障礙隨外加偏壓逐漸降低的物理過程，**不可**簡化誤解成「電壓一超過 `0.7 V` 就會瞬間出現固定電流」（電路計算用的簡化近似模型詳見 [diode-circuit-models.md](./diode-circuit-models.md)）。

### 4. 反向偏壓（Reverse Bias）
- 外加反向偏壓通常會**抑制多數載子**跨越 PN 接面，使二極體在一般應用中呈現**高阻抗**（對電流阻礙極大、幾乎不通）的阻擋狀態。
- 然而在物理實際上，反向偏壓下**仍存在少量反向電流**（漏電流），並非絕對完全無電流。

### 5. 電路層面的偏壓判讀補充（整合自 S02）
- 在電路圖上判斷正／反向偏壓時，看的是二極體**陽極 A 與陰極 K 兩端的相對電位**（詳見 [diode-symbol-and-direction.md](./diode-symbol-and-direction.md)），並須牢記正反偏概念不等於所有真實電路都等同理想開關。

---

## 相關頁面連結

- 電路符號與端點：[diode-symbol-and-direction.md](./diode-symbol-and-direction.md)
- 簡化電路分析模型：[diode-circuit-models.md](./diode-circuit-models.md)（釐清物理現象與 `0.7 V` 固定壓降模型近似之區別）
- 導通判斷步驟：[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)
- 來源摘要：[src-01-openstax-pn-junction.md](../sources/src-01-openstax-pn-junction.md)、[src-02-aac-diode-symbol.md](../sources/src-02-aac-diode-symbol.md)
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M1、M2、M3、M4）
- 返回總目錄：[index.md](../index.md)

---

## 來源溯源與已知限制

- **依據 `raw/` 檔案**：
  - `raw/S01_OpenStax_PN接面.md`（附公開教材 URL 之中文改寫導讀筆記，非原文全文）
  - `raw/S02_AAC_二極體符號方向.md`（附公開教材 URL 之中文改寫導讀筆記，非原文全文）
- **對應公開教材**：
  - OpenStax, *9.7 Semiconductor Devices*（https://openstax.org/books/university-physics-volume-3/pages/9-7-semiconductor-devices）
  - All About Circuits, *Introduction to Diodes and Rectifiers*（https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/introduction-to-diodes-and-rectifiers/）
- **目前知識邊界**：本頁涵蓋物理偏壓與符號相對電位銜接；電路簡化模型與導通判斷已由 `S03` 補充至 [diode-circuit-models.md](./diode-circuit-models.md) 與 [diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)，整流應用見 [rectification-half-and-full-wave.md](./rectification-half-and-full-wave.md)。現有來源未提供量化指數電流公式（Shockley 方程式）與反向崩潰電壓規格。
