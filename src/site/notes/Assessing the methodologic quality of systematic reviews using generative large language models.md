---
{"dg-publish":true,"permalink":"/Assessing the methodologic quality of systematic reviews using generative large language models/","title":"Assessing the methodologic quality of systematic reviews using generative large language models","tags":["chatgpt","ai","LLMAI","scoring","evaluation","method","guideline"],"created":"2025-09-03T11:13","updated":"2025-09-03T11:13"}
---


## Assessing the methodologic quality of systematic reviews using generative large language models

### 研究主旨以及結果

本研究探討 生成式大型語言模型（LLMs，例如 GPT）能否準確地使用A MeaSurement Tool to Assess systematic Reviews 2 (AMSTAR 2)評估系統性回饋（Systematic Reviews, SRs）的研究方法學品質。
結果顯示：
- 以真人專家評分結果作答案，在AMSTAR 2的16題中，使用Zero shot建立的GPT 評分者平均一致性約 75%（關鍵題目的一致性 77%，非關鍵題目的一致性73%）。研究品質的四等分分類正確率為89%。
- 在使用「[[@work stuff/Chain-of-Thought Prompting\|Chain-of-Thought Prompting]]」時，GPT 評分者的關鍵題目的一致性達 92.7%。研究品質的四等分分類正確率為93%。
- 三輪 Zero-shot 評分的 internal consistency 平均為 85%，僅在少數題目低於 75%。
- 整體而言，LLM 展現了高效且可靠的評估潛力，但作者建議作為 輔助工具，而非完全取代專家判斷。

### 研究方法重點

- 資料來源：納入 2019–2021 年間發表於五本主要泌尿科期刊（BJU International, European Urology, The Journal of Urology, Urology, World Journal of Urology）的 114 篇系統性回顧（SRs）。 
- 人工評估：由兩名獨立專家使用 AMSTAR 2 工具逐項評分，若有分歧則由第三位專家裁定。 
- AI 評估：建立客製化 GPT 工具「Urology AMSTAR 2 Quality Assessor」
	- Zero-shot：進行三輪獨立評分以計算 internal consistency。並用最後一輪的結果來計算和真人專家間的一致性等指標。
	- Chain-of-Thought Prompting：依循人類審查流程逐步提示 GPT，針對每一篇文章的關鍵題目進行一次完整的強化評估，並與真人專家結果比較。 （chain of thought prompting的內容目前尚未放上網）
- 統計分析：比較 GPT 與人工評分的一致性、敏感度、特異度、F1 分數，並計算四等分總體品質分類的準確率。（但本篇的結果並未深入說明除了一致性以外的指標）
