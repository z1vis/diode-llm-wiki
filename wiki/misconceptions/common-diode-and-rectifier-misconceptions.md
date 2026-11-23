---
id: common-diode-and-rectifier-misconceptions
title: "初學者常見錯誤與迷思排雷清單"
type: misconception
sources:
  - raw/S01_OpenStax_PN接面.md
  - raw/S02_AAC_二極體符號方向.md
  - raw/S03_LibreTexts_二極體分析模型.md
  - raw/S04_AAC_整流電路.md
  - raw/S05_AAC_橋式整流器.md
status: ingested
last_updated: 2026-11-23
---

# 初學者常見錯誤與迷思排雷清單

本頁隨每次 Ingest 持續累積零基礎學習者最容易踩坑的觀念誤區，並標註對應的正確理解與來源依據。

---

## M1｜誤以為「電壓一超過 0.7 V，二極體就會瞬間出現固定電流」

- **常見錯誤說法**：只要給二極體超過 `0.7 V`，它就會瞬間導通並流過一個固定大小的電流。
- **正確理解**：正向偏壓的物理本質是「降低載子跨越 PN 接面的障礙」，讓電流較容易通過；實際導通電流仍取決於整體外接電路條件，並非超過某個電壓就突然變成固定電流。
- **相關概念頁**：[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)
- **來源依據**：`raw/S01_OpenStax_PN接面.md`（中文改寫導讀筆記；對應 OpenStax *9.7 Semiconductor Devices*，https://openstax.org/books/university-physics-volume-3/pages/9-7-semiconductor-devices）

---

## M2｜誤以為「熱平衡就是載子完全不動」或「反向偏壓絕對零電流」

- **常見錯誤說法**：沒有接電池時 PN 接面裡面完全靜止；反接時則絕對不可能有任何電流。
- **正確理解**：
  - 熱平衡時，擴散與漂移同時存在，只是淨電流互相抵銷為零。
  - 反向偏壓會抑制多數載子跨越接面，但物理上仍會有少量反向電流，並非絕對為零。
- **相關概念頁**：[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)
- **來源依據**：`raw/S01_OpenStax_PN接面.md`（中文改寫導讀筆記；對應 OpenStax *9.7 Semiconductor Devices*，https://openstax.org/books/university-physics-volume-3/pages/9-7-semiconductor-devices）

---

## M3｜未先標記陽極 A／陰極 K，或把「正／反偏」誤解成單看某點是不是正電壓

- **常見錯誤說法**：看到二極體符號就憑感覺猜方向（把橫線端誤認成正極），或以為只要陽極接到正電壓就一定是正向偏壓。
- **正確理解**：
  - 二極體符號中**橫線側對應陰極 K**，傳統正向電流方向為 `A → K`，分析前務必先標出 `A` 與 `K`。
  - 正向與反向偏壓描述的是 **`A` 與 `K` 兩端的相對電位差**，必須同時看兩端電位，不能只看其中一端。
- **相關概念頁**：[diode-symbol-and-direction.md](../concepts/diode-symbol-and-direction.md)、[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)
- **來源依據**：`raw/S02_AAC_二極體符號方向.md`（中文改寫導讀筆記；對應 All About Circuits *Introduction to Diodes and Rectifiers*，https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/introduction-to-diodes-and-rectifiers/）

---

## M4｜把「0.7 V」當成所有二極體、所有情況下絕對不變的物理常數

- **常見錯誤說法**：所有二極體只要導通，兩端電壓就永遠精準等於 `0.7 V`。
- **正確理解**：`0.7 V` 是**矽二極體在固定壓降模型（CVD）中的入門近似值**；若需更高精確度，分段線性模型會加入斜率／等效電阻，反映真實二極體壓降會隨電流等條件改變，並非普遍恆定的物理常數。
- **相關概念頁**：[diode-circuit-models.md](../concepts/diode-circuit-models.md)、[pn-junction-and-bias.md](../concepts/pn-junction-and-bias.md)
- **來源依據**：`raw/S03_LibreTexts_二極體分析模型.md`（中文改寫導讀筆記；對應 Engineering LibreTexts *2.4 Diode Circuit Models*，https://eng.libretexts.org/Bookshelves/Electrical_Engineering/Electronics/Semiconductor_Devices_-_Theory_and_Application_%28Fiore%29/02%253A_PN_Junctions_and_Diodes/2.4%253A_Diode_Circuit_Models）

---

## M5｜只假設導通卻忘了檢查結果，或在未知導通狀態下誤用疊加原理

- **常見錯誤說法**：直接假設二極體導通、算出負電流卻照抄答案；或把多個電源拆開套用疊加原理再相加。
- **正確理解**：
  - 二極體是非線性元件，未知導通狀態前不能直接套用疊加原理。
  - 解題必須遵守「先假設 → 列式 → **檢查結果是否與假設一致**」；若假設導通卻算出反向（負）電流，代表假設錯誤，必須改假設截止重算。
- **相關流程／概念頁**：[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)、[diode-circuit-models.md](../concepts/diode-circuit-models.md)
- **來源依據**：`raw/S03_LibreTexts_二極體分析模型.md`（中文改寫導讀筆記；對應 Engineering LibreTexts *2.4 Diode Circuit Models*，https://eng.libretexts.org/Bookshelves/Electrical_Engineering/Electronics/Semiconductor_Devices_-_Theory_and_Application_%28Fiore%29/02%253A_PN_Junctions_and_Diodes/2.4%253A_Diode_Circuit_Models）

---

## M6｜以為「交流電經過整流就會直接變成一條平坦的直流直線」

- **常見錯誤說法**：只要接上整流電路，輸出的直流電壓就是穩定不變的平直電壓。
- **正確理解**：整流的作用是把交流電變成**固定極性的脈動輸出**（方向不反轉，但電壓仍會隨時間高低起伏）；它**不等於**無漣波的平滑 DC，若需要平滑直流還須加上濾波電路。
- **相關概念頁**：[rectification-half-and-full-wave.md](../concepts/rectification-half-and-full-wave.md)
- **來源依據**：`raw/S04_AAC_整流電路.md`（中文改寫導讀筆記；對應 All About Circuits *Rectifier Circuits*，https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/rectifier-circuits/）

---

## M7｜混淆半波整流與全波整流的輸出脈動頻率

- **常見錯誤說法**：不管半波還是全波整流，輸出的波形重複頻率都跟原本交流電頻率 `f` 一樣。
- **正確理解**：對於頻率為 `f` 的理想正弦輸入：
  - **半波整流**每個週期只保留 1 個半波，輸出脈動頻率為 **`f`**。
  - **全波整流**把負半週也翻正成同極性，每個週期出現 2 個脈動波峰，因此輸出脈動頻率為 **`2f`**。
- **相關概念頁**：[rectification-half-and-full-wave.md](../concepts/rectification-half-and-full-wave.md)
- **來源依據**：`raw/S04_AAC_整流電路.md`（中文改寫導讀筆記；對應 All About Circuits *Rectifier Circuits*，https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/rectifier-circuits/）

---

## M8｜誤以為橋式整流器是「四顆二極體同時導通」，或計算輸出時只扣「一顆」壓降

- **常見錯誤說法**：橋式整流有四顆二極體，所以通電時四顆一起導通；或是套公式時只減一個 `0.7 V`（寫成 `|v_s| − 0.7 V`）。
- **正確理解**：
  - 在每個正常導通半週，只有**一對（兩顆）**二極體串聯導通形成閉合迴路，另兩顆處於反向偏壓截止（絕非四顆同時導通）。
  - 因此在固定壓降模型（CVD）、電阻負載、無濾波簡化條件下，總正向壓降為 **`2 × V_F`**，輸出電壓約為 `max(|v_s| − 2 V_F, 0)`（例如 `|v_s| = 10 V` 且單顆近似 `0.7 V` 時，輸出約 `8.6 V` 而非 `9.3 V`）。
- **相關概念／流程頁**：[bridge-rectifier.md](../concepts/bridge-rectifier.md)、[bridge-current-path-tracing.md](../procedures/bridge-current-path-tracing.md)
- **來源依據**：`raw/S05_AAC_橋式整流器.md`（中文改寫導讀筆記；對應 All About Circuits *Si Lab - Full-wave Bridge Rectifier*，https://www.allaboutcircuits.com/textbook/experiments/chpt-5/full-wave-bridge-rectifier/）

---

## M9｜只背公式卻未核對負載極性，誤以為負半週流過負載的電流也會反向

- **常見錯誤說法**：既然交流輸入在負半週方向反轉了，那流過負載電阻的電流方向應該也會跟著反轉吧？
- **正確理解**：橋式整流器透過四顆二極體的對稱方向配置，在正半週由 `D1、D2` 導通、負半週改由 `D3、D4` 導通，使兩個半週電流都由 `V_out+` 進入負載、從 `V_out−` 離開，**負載兩端極性與電流方向維持一致**。
- **相關概念／流程頁**：[bridge-current-path-tracing.md](../procedures/bridge-current-path-tracing.md)、[bridge-rectifier.md](../concepts/bridge-rectifier.md)
- **來源依據**：`raw/S05_AAC_橋式整流器.md`（中文改寫導讀筆記；對應 All About Circuits *Si Lab - Full-wave Bridge Rectifier*，https://www.allaboutcircuits.com/textbook/experiments/chpt-5/full-wave-bridge-rectifier/）
