---
id: curriculum-order
title: "跨來源綜合：零基礎初學者教學順序與知識對照"
type: synthesis
sources:
  - raw/S01_OpenStax_PN接面.md
  - raw/S02_AAC_二極體符號方向.md
  - raw/S03_LibreTexts_二極體分析模型.md
  - raw/S04_AAC_整流電路.md
  - raw/S05_AAC_橋式整流器.md
status: ingested
last_updated: 2026-11-23
---

# 跨來源綜合：零基礎初學者教學順序與知識對照

本頁整合 5 份 `raw/` 來源（皆為附公開教材 URL 的中文改寫導讀筆記），為沒有電子學基礎、僅具電壓／電流／歐姆定律先備知識的讀者，規劃循序漸進的學習路徑，作為後續 Query 與 `outputs/index.html` 教學簡報的結構骨幹。

---

## 五階段學習順序（由直覺到橋式整流實戰）

| 學習階段 | 核心問題（零基礎視角） | 對應 Wiki 頁面 | 對應原始來源 | 必避開之關鍵迷思 |
| :--- | :--- | :--- | :--- | :--- |
| **階段 1：物理直覺與符號** | 二極體為什麼只讓單向電流容易通過？電路圖上哪端是陽極 `A`、哪端是陰極 `K`？ | [pn-junction-and-bias.md](./concepts/pn-junction-and-bias.md)<br>[diode-symbol-and-direction.md](./concepts/diode-symbol-and-direction.md) | `S01`、`S02` | M1（非瞬間固定電流）、M2（反偏非絕對零電流）、M3（橫線端是陰極 K，偏壓看相對電位） |
| **階段 2：簡化電路模型** | 真實二極體是非線性的，怎麼用入門數學算電路？`0.7 V` 到底是什麼？ | [diode-circuit-models.md](./concepts/diode-circuit-models.md) | `S03`（銜接 `S01`、`S02`） | M4（`0.7 V` 是矽 CVD 模型近似條件，非恆定物理常數） |
| **階段 3：導通判斷 SOP** | 拿到一個含二極體的電路，怎麼一步步確認它到底導通還是截止？ | [diode-conduction-assume-and-check.md](./procedures/diode-conduction-assume-and-check.md) | `S02`、`S03` | M5（不可未知狀態直接套疊加原理；假設後務必驗算） |
| **階段 4：半波與全波整流** | 交流電怎麼變成單向脈動電壓？半波與全波波形和頻率差在哪裡？ | [rectification-half-and-full-wave.md](./concepts/rectification-half-and-full-wave.md) | `S04`（銜接 `S02`） | M6（固定極性脈動輸出 ≠ 平滑 DC）、M7（半波 `f` vs 全波 `2f`） |
| **階段 5：橋式整流與壓降** | 四顆二極體怎麼分工讓兩半週負載電流同向？為什麼要扣 `2 V_F`？ | [bridge-rectifier.md](./concepts/bridge-rectifier.md)<br>[bridge-current-path-tracing.md](./procedures/bridge-current-path-tracing.md) | `S05`（整合 `S02`～`S04`） | M8（每半週兩顆導通扣 `2 V_F`，非四顆導通也非一顆）、M9（兩半週負載電流方向一致） |

---

## 跨來源知識演化重點（體現 LLM Wiki 整合價值）

1. **從「定性單向性」演進到「近似量化模型」**：`S01`（PN 接面障礙降低）→ `S02`（止回閥類比但非完美開關）→ `S03`（理想／CVD `0.7 V` 近似／分段線性三層模型）→ `S05`（在 CVD 簡化前提下套用 `2 V_F` 計算橋式整流輸出）。
2. **從「單顆二極體判斷」演進到「四顆橋式協作」**：`S02` 的「先標記 A/K」＋ `S03` 的「先假設再驗證」直接延伸成為 `S05` 的「正負半週兩兩配對追蹤與負載極性核對」。
3. **一致的教學邊界聲明**：本知識庫不跨越現有 5 份來源擅自編造指數型 Shockley 公式、電容濾波 RC 計算或元件反向耐壓規格，所有缺口皆於各頁透明標註。
