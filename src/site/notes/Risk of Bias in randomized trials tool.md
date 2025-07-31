---
{"dg-publish":true,"permalink":"/Risk of Bias in randomized trials tool/","title":"Risk of Bias in randomized trials tool","tags":["guideline"],"created":"2025-06-30T12:10","updated":"2025-06-30T14:22"}
---


目前最新版為2019年8月22修訂的[版本](https://drive.google.com/file/d/18Zks7k4kxhbUUlbZ51Ya5xYa3p3ECQV0/view)操作手冊。包含 5 Domain以及一個overall的評分。

## domain level

包一個domain包含3至5題，每一題的評分：
1. Yes (是)
2. Probably yes (可能是)
3. Probably no (可能不是)
4. No (不是)
5. No information (無資訊)


> [!Attention] Domain中每一題的評分
> Responses of ‘Yes’ and ‘Probably yes’ have the same implications for risk of bias, as do responses of ‘No’ and ‘Probably no’. The definitive versions (‘Yes’ and ‘No’) would typically imply that firm evidence is available in relation to the signalling question; the ‘Probably’ versions would typically imply that a judgement has been made. If review authors calculate measures of agreement (e.g. kappa statistics) for the answers to the signalling questions, we recommend treating ‘Yes’ and ‘Probably yes’ as the same response and ‘No’ and ‘Probably no’ as the same response.


- Domain 1: Risk of bias arising from the randomization process
- Domain 2: Risk of bias due to deviations from the intended interventions （舊版稱為執行偏誤，performance bias）
	- effect of assignment to intervention (intention-to-treat effect): 評估的是一旦被隨機分配到某介入組，無論參與者是否實際接受該介入，其所產生的效果。這種效果估計對於回答「是否推薦在特定醫療系統中實施某項介入政策」等公共衛生問題更為相關。
	- effect of adhering to intervention: 評估的是如果參與者能夠完全按照計畫所規劃的介入，那麼該介入會產生的效果。這種效果估計對於「個人患者的照護決策」可能更直接相關。
- Domain 3: Missing outcome data
- Domain 4: Risk of bias in measurement of the outcome
- Domain 5: Risk of bias in selection of the reported result


> [!NOTE] Domain 2
> 試驗期間為了參與者安全或健康狀況變化而依循試驗方案預設的介入調整（例如，類風濕性關節炎患者因嚴重毒性而更換藥物，或癌症患者因病情進展而轉為二線介入）不應被視為偏離預期介入。然而，研究者有時並未充分說明所有允許的介入調整，這可能需要評估者自行判斷哪些變動是符合原先研究計畫的意圖。

每一個domain，這個手冊提供了決策樹，說明如何根據題目的結果來判斷該domain可能有bias的風險，包含Low / Some / High  三個等級的評分。
決策樹範例如下：
![Pasted image 20250630141725.png](/img/user/Pasted%20image%2020250630141725.png)

### overall risk of bias

- low risk:
	- 所有的domain都是低風險
- some concerns:
	- 至少一個domain被評為some concerns，但沒有任何domain被評為high risk
- high risk:
	- 至少一個domain被評為high risk
	- 在數個domain被評為some concerns