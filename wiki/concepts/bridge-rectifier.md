---
id: bridge-rectifier
title: "橋式整流器（Full-Wave Bridge Rectifier）結構、導通對與 2VF 壓降"
type: concept
sources:
  - raw/S05_AAC_橋式整流器.md
  - raw/S04_AAC_整流電路.md
  - raw/S03_LibreTexts_二極體分析模型.md
  - raw/S02_AAC_二極體符號方向.md
status: ingested
last_updated: 2026-11-23
---

# 橋式整流器（Full-Wave Bridge Rectifier）

## 一句話白話理解（給零基礎者）

橋式整流器像一座由**四道單向閘門（四顆二極體）組成的智慧立交橋**：不管外面馬路的車流（交流電）往哪個方向開進來，每次都由**其中兩道順向閘門接力引導、另兩道自動關閉**，讓通過橋中央負載的車流**永遠只朝同一個方向前進**。

---

## 核心概念與電路意義

### 1. 四顆二極體的橋式分工
為便於初學者追蹤電流，以下採用標準教學編號（`D1`～`D4` 為教學標記慣例，對應 S05 所述之兩對交替導通二極體）：
- 交流輸入端：`AC+`、`AC−`
- 負載電阻 `R_L` 兩端：正輸出端 `V_out+`、負輸出端 `V_out−`
- 連接方向（依 [diode-symbol-and-direction.md](./diode-symbol-and-direction.md) 標示 `A → K`）：
  - `D1`：`AC+`（A）→ `V_out+`（K）
  - `D2`：`V_out−`（A）→ `AC−`（K）
  - `D3`：`AC−`（A）→ `V_out+`（K）
  - `D4`：`V_out−`（A）→ `AC+`（K）

### 2. 每正常導通半週：只經過「兩顆」二極體，絕非四顆同時導通
- **正半週**（`AC+` 電位高於 `AC−`，且超過兩顆導通門檻）：
  - **導通對**：`D1` 與 `D2` 串聯導通；`D3` 與 `D4` 反向偏壓截止。
  - **迴路**：`AC+` → `D1` → `V_out+` → **負載 `R_L`（`V_out+ → V_out−`）** → `V_out−` → `D2` → `AC−`。
- **負半週**（`AC−` 電位高於 `AC+`，且超過兩顆導通門檻）：
  - **導通對**：`D3` 與 `D4` 串聯導通；`D1` 與 `D2` 反向偏壓截止。
  - **迴路**：`AC−` → `D3` → `V_out+` → **負載 `R_L`（`V_out+ → V_out−`）** → `V_out−` → `D4` → `AC+`。
- **關鍵觀察**：兩個半週流過負載 `R_L` 的電流方向**完全一致**（皆由 `V_out+` 流向 `V_out−`），達成全波整流（理想正弦輸入頻率 `f` 時，輸出脈動頻率為 `2f`，見 [rectification-half-and-full-wave.md](./rectification-half-and-full-wave.md)）。

### 3. 簡化模型下的輸出電壓與「兩倍壓降（2 V_F）」
在以下三個明確前提同時成立時：
1. 採用**固定壓降模型（CVD）**（單顆矽二極體常近似 `V_F ≈ 0.7 V`，見 [diode-circuit-models.md](./diode-circuit-models.md)）
2. 負載為**純電阻負載**
3. **未加濾波電路**

負載端瞬間輸出電壓約為：
$$v_o(t) \approx \max\bigl(|v_s(t)| - 2 V_F,\; 0\bigr)$$

- **為什麼要減去 `2 V_F`（約 `1.4 V`）？**  
  因為每個正常導通半週的完整電流迴路都串聯經過**兩顆**二極體（正半週過 `D1`、`D2`；負半週過 `D3`、`D4`），每顆二極體在 CVD 模型下各產生約 `V_F` 的正向壓降。
- **當 `|v_s(t)| ≤ 2 V_F` 時（死區，dead zone）**：  
  在每個正弦半週接近零交越處，輸入電壓短暫低於兩顆串聯二極體的近似門檻總和（`2 V_F`），四顆二極體皆視為截止，輸出呈現一段近似 `0 V` 的空檔區間（即「死區」）。
- **簡化估算例**：若輸入瞬間電壓絕對值 `|v_s| = 10 V`，且以矽二極體 CVD 模型近似 `V_F ≈ 0.7 V`：
  $$v_o \approx 10\text{ V} - 2 \times 0.7\text{ V} = 8.6\text{ V}$$
  （再次提醒：`0.7 V` 為矽二極體固定壓降模型近似條件，且整流後輸出仍為固定極性脈動波形，非平滑直流。）

---

## 相關頁面連結

- 上游概念：[rectification-half-and-full-wave.md](./rectification-half-and-full-wave.md)、[diode-circuit-models.md](./diode-circuit-models.md)、[diode-symbol-and-direction.md](./diode-symbol-and-direction.md)
- 路徑追蹤步驟：[bridge-current-path-tracing.md](../procedures/bridge-current-path-tracing.md)
- 通用導通判斷：[diode-conduction-assume-and-check.md](../procedures/diode-conduction-assume-and-check.md)
- 對應常見錯誤：[common-diode-and-rectifier-misconceptions.md](../misconceptions/common-diode-and-rectifier-misconceptions.md)（見 M4、M6、M7、M8、M9）
- 來源摘要：[src-05-aac-bridge-rectifier.md](../sources/src-05-aac-bridge-rectifier.md)
- 返回總目錄：[index.md](../index.md)

---

## 來源溯源與已知限制

- **主要依據 `raw/` 檔案**：`raw/S05_AAC_橋式整流器.md`（中文改寫導讀筆記，非原文全文）；整合關聯 `S02`、`S03`、`S04`。
- **對應公開教材**：All About Circuits, *Si Lab - Full-wave Bridge Rectifier*（https://www.allaboutcircuits.com/textbook/experiments/chpt-5/full-wave-bridge-rectifier/）
- **已知限制**：上述公式僅適用於 CVD 模型、純電阻負載與未加濾波條件；現有來源未涵蓋電容濾波後波形與漣波量化計算、元件反向耐壓（PIV）選型與示波器共地接線議題。
