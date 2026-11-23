# Wiki 執行日誌（Append-Only Log）

> 本日誌採**只追加、不回頭竄改**原則，忠實記錄每一次架構建立、逐篇 Ingest、增量檢查、Query、Lint 與後續修正事件。  
> 所有未執行項目不提前填寫；`raw/` 內的 5 份檔案皆為附公開教材 URL 的中文改寫導讀筆記（非原文全文）。

---

## [2026-11-23 22:27] INIT | 建立操作憲法與 Wiki 基礎架構

- **觸發依據**：使用者確認第一階段唯讀盤點結果，並授權第二階段（建立 `AGENTS.md`、`wiki/` 並依 `S01` → `S05` 逐篇執行 5 次 Ingest）。
- **新增檔案**：
  - `AGENTS.md`（規範資料夾邊界、誠信底線、頁面 Schema、Ingest/Query/Lint/雙迴圈 HTML 生成規則）
  - `wiki/index.md`（初始化總索引，目前進度 `0 / 5`）
  - `wiki/log.md`（初始化 append-only 執行日誌）
- **保留未動**：`raw/`、`reference/`、`flow/`、`evidence/` 及根目錄 `00_`～`05_` 檔案均未修改。
- **下一步**：依序實際讀取 `raw/S01_OpenStax_PN接面.md`，開始第 1 次 Ingest。

---

## [2026-11-23 22:28] INGEST #1 | `raw/S01_OpenStax_PN接面.md`

- **原始文件與來源性質**：`raw/S01_OpenStax_PN接面.md`（中文改寫導讀筆記，非原文全文）
- **對應公開教材 URL**：https://openstax.org/books/university-physics-volume-3/pages/9-7-semiconductor-devices
- **實際擷取重點**：
  - P/N 半導體接觸時由載子擴散與內建電場形成空乏區。
  - 熱平衡為擴散與漂移淨電流相抵之動態平衡。
  - 正向偏壓降低跨越障礙利於導通；反向偏壓抑制多數載子但仍有少量反向電流。
  - 避免把正向導通誤解成超過 `0.7 V` 瞬間出現固定電流。
- **新增／更新檔案**：
  - 新增 `wiki/sources/src-01-openstax-pn-junction.md`
  - 新增 `wiki/concepts/pn-junction-and-bias.md`
  - 新增 `wiki/misconceptions/common-diode-and-rectifier-misconceptions.md`（新增 M1、M2）
  - 更新 `wiki/index.md`（進度 `1 / 5`）
- **交叉連結更新**：`src-01` ↔ `pn-junction-and-bias` ↔ `common-diode-and-rectifier-misconceptions` ↔ `index.md`。
- **增量檢查結果（Incremental Lint）**：
  - 連結與來源標示完整；已明確標註為改寫導讀筆記及來源未涵蓋項目（無指數電流公式、無崩潰電壓數值）。
  - 尚待後續來源補齊電路符號極性與分析模型。

---

## [2026-11-23 22:29] INGEST #2 | `raw/S02_AAC_二極體符號方向.md`

- **原始文件與來源性質**：`raw/S02_AAC_二極體符號方向.md`（中文改寫導讀筆記，非原文全文）
- **對應公開教材 URL**：https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/introduction-to-diodes-and-rectifiers/
- **實際擷取重點**：
  - 二極體具單向導通特性（可類比為止回閥），正向傳統電流方向為陽極 `A →` 陰極 `K`。
  - 符號橫線端對應陰極 `K`，電路分析前應先標記端點。
  - 正／反向偏壓為兩端相對電位的描述，不代表所有實際情況都能以理想開關精確表示。
  - 繪製 HTML 符號須特別核對陰極橫線端位置。
- **新增／更新檔案**：
  - 新增 `wiki/sources/src-02-aac-diode-symbol.md`
  - 新增 `wiki/concepts/diode-symbol-and-direction.md`
  - 更新 `wiki/concepts/pn-junction-and-bias.md`（整合「相對端電位」補充並建立雙向連結）
  - 更新 `wiki/misconceptions/common-diode-and-rectifier-misconceptions.md`（新增 M3）
  - 更新 `wiki/index.md`（進度 `2 / 5`）
- **交叉連結更新**：`src-02` ↔ `diode-symbol-and-direction` ↔ `pn-junction-and-bias` ↔ `common-diode-and-rectifier-misconceptions` ↔ `index.md`。
- **增量檢查結果（Incremental Lint）**：
  - S01 與 S02 無觀念矛盾，順利將「物理偏壓」銜接至「電路符號極性與相對電位」。
  - 已標記未涵蓋處（實體零件色環標記、電路數學模型尚待 S03）。

---

## [2026-11-23 22:31] INGEST #3 | `raw/S03_LibreTexts_二極體分析模型.md`

- **原始文件與來源性質**：`raw/S03_LibreTexts_二極體分析模型.md`（中文改寫導讀筆記，非原文全文）
- **對應公開教材 URL**：https://eng.libretexts.org/Bookshelves/Electrical_Engineering/Electronics/Semiconductor_Devices_-_Theory_and_Application_%28Fiore%29/02%253A_PN_Junctions_and_Diodes/2.4%253A_Diode_Circuit_Models
- **實際擷取重點**：
  - 二極體屬非線性元件，未知導通狀態前不可直接對電路套用疊加原理。
  - 區分三種模型：理想模型（ON 短路／OFF 開路）、固定壓降模型（CVD，矽二極體入門常近似 `0.7 V`）、分段線性模型（加斜率／等效電阻）。
  - 強化 `0.7 V` 僅為特定近似模型條件，真實二極體壓降非在所有電流下皆固定。
  - 建立「先假設導通狀態 → 列式求解 → 檢查結果是否符合假設」流程。
- **新增／更新檔案**：
  - 新增 `wiki/sources/src-03-libretexts-diode-models.md`
  - 新增 `wiki/concepts/diode-circuit-models.md`
  - 新增 `wiki/procedures/diode-conduction-assume-and-check.md`
  - 更新 `wiki/concepts/pn-junction-and-bias.md`、`wiki/concepts/diode-symbol-and-direction.md`（補齊模型與流程交叉連結）
  - 更新 `wiki/misconceptions/common-diode-and-rectifier-misconceptions.md`（新增 M4、M5）
  - 更新 `wiki/index.md`（進度 `3 / 5`）
- **交叉連結更新**：`src-03` ↔ `diode-circuit-models` ↔ `diode-conduction-assume-and-check` ↔ `pn-junction-and-bias` / `diode-symbol-and-direction` / `common-diode-and-rectifier-misconceptions` ↔ `index.md`。
- **增量檢查結果（Incremental Lint）**：
  - 成功釐清 S01（物理定性障礙降低）與 S03（CVD `0.7 V` 近似模型）間的關係，避免概念混淆。
  - 已於流程頁明確區分「S03 來源原則」與「結合基礎歐姆定律之教學演算示意」，未冒稱為來源原文內容。

---

## [2026-11-23 22:32] INGEST #4 | `raw/S04_AAC_整流電路.md`

- **原始文件與來源性質**：`raw/S04_AAC_整流電路.md`（中文改寫導讀筆記，非原文全文）
- **對應公開教材 URL**：https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/rectifier-circuits/
- **實際擷取重點**：
  - 整流係利用二極體單向性，將交流輸入轉為負載端固定極性的脈動輸出。
  - 半波整流僅用單一半週，理想正弦輸入下脈動頻率為 `f`；全波整流利用正負兩半週，輸出脈動頻率為 `2f`。
  - 整流不等於無漣波平滑 DC，若需平滑直流仍須濾波。
- **新增／更新檔案**：
  - 新增 `wiki/sources/src-04-aac-rectifier-circuits.md`
  - 新增 `wiki/concepts/rectification-half-and-full-wave.md`
  - 更新 `wiki/concepts/diode-symbol-and-direction.md`、`wiki/concepts/diode-circuit-models.md`（補上整流應用交叉連結）
  - 更新 `wiki/misconceptions/common-diode-and-rectifier-misconceptions.md`（新增 M6、M7）
  - 更新 `wiki/index.md`（進度 `4 / 5`）
- **交叉連結更新**：`src-04` ↔ `rectification-half-and-full-wave` ↔ `diode-symbol-and-direction` / `diode-circuit-models` / `common-diode-and-rectifier-misconceptions` ↔ `index.md`。
- **增量檢查結果（Incremental Lint）**：
  - 脈動頻率（半波 `f`、全波 `2f`）與「固定極性 ≠ 平滑 DC」已清楚區分。
  - 已註明未涵蓋濾波電容 RC 量化計算與橋式整流具體電路（交由 S05 補齊）。

---

## [2026-11-23 22:34] INGEST #5 | `raw/S05_AAC_橋式整流器.md`

- **原始文件與來源性質**：`raw/S05_AAC_橋式整流器.md`（中文改寫導讀筆記，非原文全文）
- **對應公開教材 URL**：https://www.allaboutcircuits.com/textbook/experiments/chpt-5/full-wave-bridge-rectifier/
- **實際擷取重點**：
  - 橋式整流採四顆二極體配置，使正、負兩交流半週流過負載的電流方向保持一致。
  - 每個正常導通半週的完整迴路僅經過**兩顆**串聯二極體（另一對截止），絕非四顆同時導通。
  - 在固定壓降模型（CVD）、電阻負載、未加濾波條件下，負載端瞬間電壓約為 `max(|v_s| − 2V_F, 0)`，須核對總正向壓降 `2 × V_F` 與負載極性／電流方向。
- **新增／更新檔案**：
  - 新增 `wiki/sources/src-05-aac-bridge-rectifier.md`
  - 新增 `wiki/concepts/bridge-rectifier.md`
  - 新增 `wiki/procedures/bridge-current-path-tracing.md`
  - 新增 `wiki/curriculum-order.md`（跨 5 份來源的零基礎教學順序綜合頁）
  - 更新 `wiki/concepts/rectification-half-and-full-wave.md`、`wiki/concepts/diode-circuit-models.md`、`wiki/procedures/diode-conduction-assume-and-check.md`（補齊與橋式整流之雙向交叉連結）
  - 更新 `wiki/misconceptions/common-diode-and-rectifier-misconceptions.md`（新增 M8、M9）
  - 更新 `wiki/index.md`（進度 `5 / 5`，完成五篇 Ingest）
- **交叉連結更新**：`src-05` ↔ `bridge-rectifier` ↔ `bridge-current-path-tracing` ↔ `rectification-half-and-full-wave` / `diode-circuit-models` / `diode-conduction-assume-and-check` / `common-diode-and-rectifier-misconceptions` / `curriculum-order` ↔ `index.md`。
- **增量檢查結果（Incremental Lint）**：
  - 5 份 `raw/` 來源已全數完成逐篇 Ingest；已明確標示 `D1`～`D4` 為標準教學編號慣例，並標出未涵蓋處（PIV 選型、電容濾波量化、示波器共地）。
  - 尚未執行第三階段之正式全庫 Lint、Query 實測與 `outputs/index.html` 生成，等待使用者確認本階段成果。

---

## [2026-11-23 22:38] QUERY | 第三階段三組實測查詢（Q1～Q3）

- **查閱路徑**：先讀取 `wiki/index.md`、`wiki/log.md` 與 `AGENTS.md`，再依索引讀取 `diode-conduction-assume-and-check.md`、`diode-circuit-models.md`、`diode-symbol-and-direction.md`、`pn-junction-and-bias.md`、`rectification-half-and-full-wave.md`、`bridge-rectifier.md`、`bridge-current-path-tracing.md`、`common-diode-and-rectifier-misconceptions.md`。
- **執行查詢**：
  - **Q1**：固定壓降模型下二極體導通判斷之假設、計算、驗證完整步驟（引用 `S02`、`S03`）。
  - **Q2**：理想模型與固定壓降模型差異、適用情境與 `0.7 V` 適用條件（引用 `S01`、`S03`、`S05`）。
  - **Q3**：橋式全波整流器正／負半週導通二極體對與負載電流同向原因（引用 `S02`、`S04`、`S05`）。
- **記錄檔案**：新增 `reports/query-verification.md`（每題均含引用 Wiki 頁、原始來源 URL、完整解答與知識缺口清單）。
- **查詢過程順帶發現之潛在問題**：Q1 查閱時發現 `diode-conduction-assume-and-check.md` 的 OFF 邊界條件（`< V_F`）與 `bridge-rectifier.md`（`≤ 2 V_F`）在等號邊界略不一致，留待即將執行的全庫 Lint 檢查一併核對。

---

## [2026-11-23 22:39] LINT #1 (Before Fix) | 全庫健康檢查發現 4 項待修正問題

- **檢查範圍**：`wiki/` 共 16 個檔案。
- **通過項目**：內部相對連結（0 斷裂）、孤兒頁（0 孤兒）、5 篇 `raw/` 覆蓋與改寫性質標示、二極體極性與橋式兩顆串聯導通路徑、`0.7 V` 近似限定、半波 `f`／全波 `2f` 與脈動／平滑 DC 區分均通過。
- **發現原始問題（Fail）**：
  1. `L-01`：`pn-junction-and-bias.md`（L32、L62）與 `diode-symbol-and-direction.md`（L40、L60）殘留前期 Ingest 留下的「待後續／待 S03 補齊」過期語句。
  2. `L-02`：5 份概念／流程頁中存在對零基礎讀者未附白話解釋的術語（載子、擴散、漂移、高阻抗、短路、開路、疊加原理、KVL/KCL、漣波、濾波、死區）。
  3. `L-03`：`common-diode-and-rectifier-misconceptions.md` 的 M4～M9 漏列對應公開教材 URL（與 M1～M3 格式不一致）。
  4. `L-04`：`diode-conduction-assume-and-check.md` 第 4 步 CVD 截止驗證邊界（`< V_F`）與 `bridge-rectifier.md`（`≤ 2 V_F`）等號邊界未統一。
- **記錄位置**：`reports/lint-report.md`（已保留原始問題紀錄）。
- **下一步**：依 `flow/workflow.mmd` 退回修正對應 Wiki 頁面，再執行 Lint 複查。

---

## [2026-11-23 22:40] FIX | 修正 Lint #1 發現之 4 項 Wiki 問題（L-01～L-04）

- **修正檔案**：
  - `wiki/concepts/pn-junction-and-bias.md`（修正 `L-01` 過期語句、`L-02` 補白話術語）
  - `wiki/concepts/diode-symbol-and-direction.md`（修正 `L-01` 過期語句並補橋式連結）
  - `wiki/concepts/diode-circuit-models.md`（修正 `L-02` 補短路／開路／疊加原理白話解釋）
  - `wiki/procedures/diode-conduction-assume-and-check.md`（修正 `L-02` 補 KVL/KCL 白話解釋、`L-04` 統一 `V_D ≤ V_F` 邊界）
  - `wiki/concepts/rectification-half-and-full-wave.md`（修正 `L-02` 補漣波／濾波白話解釋）
  - `wiki/concepts/bridge-rectifier.md`（修正 `L-02` 補死區白話解釋）
  - `wiki/misconceptions/common-diode-and-rectifier-misconceptions.md`（修正 `L-03` 補齊 M4～M9 公開教材 URL）

---

## [2026-11-23 23:12] GENERATE | 生成教學 HTML 簡報與流程反思

- **觸發依據**：使用者因作業即將截止，指示停止非必要重跑循環，直接依據既有 `wiki/`、`raw/`、`AGENTS.md` 與 Q1–Q3 成果優先生成 `outputs/index.html` 與 `reports/workflow-reflection.md`。
- **新增／更新檔案**：
  - 新增 `outputs/index.html`（12 頁淺色專業教學風單檔簡報，含鍵盤／按鈕翻頁、PN 接面與符號 SVG、Q1–Q3 教學頁、CVD 導通互動滑桿、半波 `f` vs 全波 `2f` 波形 SVG、橋式整流正／負半週／死區互動電路圖、3 題互動測驗與每頁 Wiki 來源頁腳）
  - 新增 `reports/workflow-reflection.md`（記錄 5 次 Ingest、Query、Lint 發現與修正、Loop/Graph 流程與製作心得）
  - 更新 `reports/lint-report.md`、`wiki/index.md`
- **保留未動**：`raw/`、`reference/`、`flow/`、`evidence/` 及 `00_`～`05_` 皆未修改。
- **誠實測試註記**：檔案已實際寫入磁碟，尚未執行自動化瀏覽器截圖測試，請直接以瀏覽器開啟 `outputs/index.html` 驗證並截圖存證。
