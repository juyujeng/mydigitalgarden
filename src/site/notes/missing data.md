---
{"dg-publish":true,"permalink":"/missing data/","title":"遺漏值的類型","tags":["guideline","statistics"],"created":"2026-10-06T09:45","updated":"2026-10-06T10:30","dg-note-properties":{"date":"2026-10-06T09:45","lastmod":"2026-10-06T10:30","title":"遺漏值的類型","aliases":["missing data"],"tags":["guideline","statistics"]}}
---


### 1. 完全隨機遺漏（Missing Completely at Random, MCAR）

- **定義**：資料遺漏的機率與**任何變數都無關**，既不受已觀察變數（$Y_{obs}, X$）影響，也不受未觀察數值本身（$Y_{mis}$）影響。
- **具體情境**：
	- 問卷在郵寄過程中隨機遺失。
	- 實驗室檢驗試管隨機打破。
	- 受試者因為搬家到國外而中斷追蹤（且搬家原因與研究疾病、治療或任何人口學變項毫無關聯）。
- **統計後果與處理**：
	- **完整案例分析（Complete Case Analysis / Listwise Deletion）** 仍能獲得不偏（unbiased）的參數估計值，但會損失樣本數，導致統計檢定力（Power）下降與標準誤變大。
	- 可透過 Little's MCAR test 來檢定資料是否符合此假設。

### 2. 隨機遺漏（Missing at Random, MAR）

- **定義**：資料遺漏的機率**僅與「已觀察變數」有關**，但在控制了這些已觀察變數之後，遺漏與未觀察到的真實數值彼此獨立（無關）。
- **具體情境**：
	- **追蹤研究中**：男性比女性更容易漏填憂鬱量表，但在「男性」這個族群內部，憂鬱分數高低並不會改變其漏填的機率。
	- 年長者在第 3 次追蹤時的回訪率較低，但只要把「年齡」納入模型控制，遺漏機率就與該時間點的真實健康狀態無關。
- **統計後果與處理**：
	- 若直接刪除遺漏值（Listwise Deletion），估計結果將會產生**系統性偏誤（Biased）**。
	- **現代統計標準方法**（如多重補值法 **Multiple Imputation, MI**、完全資訊最大概似法 **Full Information Maximum Likelihood, FIML**，或追蹤資料常用的 **MMRM / 線性混合模型 LMM**）在 MAR 假設下均可產出不偏（unbiased）且有效（valid）的參數估計與推論。
	- MAR 本身通常無法直接以現有資料進行檢定（non-testable），需要仰賴領域知識與敏感度分析。

### 3. 非隨機遺漏（Missing Not at Random, MNAR）

- **定義**：資料遺漏的機率**直接與「該變數未觀察到的數值本身」有關**，即使控制了所有已觀察變數，遺漏仍無法被完全解釋（又稱為 Informative Missingness 或 Non-ignorable Missingness）。
- **具體情境**：
	- 高收入者或極低收入者刻意拒絕透露收入。
	- 在藥物臨床試驗或長照追蹤中，病情惡化嚴重的患者因虛弱、副作用或死亡而退出追蹤；或是憂鬱症極度嚴重的患者因失去動力而未回傳量表。
- **統計後果與處理**：
	- 這是最棘手的情形。傳統的 Listwise Deletion、單一補值法（如 LOCF），甚至標準的 MI 與 MMRM 都會產生偏誤。
	- 需要建立特定的聯合模型（Joint Modeling），例如：
		- **選擇模型（Selection Models）**：如 Heckman 兩階段修正、Diggle-Kenward 模型。
		- **模式混合模型（Pattern-Mixture Models）**：依據不同的退出時間或遺漏模式分組建立模型。
		- **共享參數模型（Shared-Parameter Models）**：使用潛在變項（Latent Variable）同時連結測量軌跡與遺漏過程。
	- 實務上多搭配**敏感度分析（Sensitivity Analysis / Tipping-point analysis）**，評估當資料偏離 MAR 時，研究結論是否依然穩健。

### 三種遺漏資料機制特性、分析影響與處理策略對照表


| **機制**   | **遺漏機率取決於**          | **直接刪除（只使用Complete Case 分析）** | **套用標準方法（MI / MMRM）的效果**     |
| :------- | :------------------- | :---------------------------- | :--------------------------- |
| **MCAR** | 完全隨機，與任何變數皆無關        | 不偏（Unbiased），但損失樣本數與檢定力       | **可用且更佳**（善用所有已觀察資料，估計更有效率）  |
| **MAR**  | 已觀察變數（$Y_{obs}, X$）  | **有偏誤（Biased）**               | **最佳解**（可得出不偏且有效的估計與推論）      |
| **MNAR** | 未觀察到的數值本身（$Y_{mis}$） | **有偏誤（Biased）**               | **無效／仍有偏誤**（需改用特定聯合模型或敏感度分析） |