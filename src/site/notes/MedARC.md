---
{"dg-publish":true,"permalink":"/MedARC/","title":"MedARC (Medical Agent Refinement & Collaboration)","tags":["guideline","LLMAI","chatgpt","virtual-patient","OSCE"],"created":"2025-10-20T10:40","updated":"2025-10-21T14:56"}
---


MedARC (Medical Agent Refinement & Collaboration)

MedARC 的運作流程可分為三個主要階段是一種新穎的多代理人框架，目標在透過結構化辯論來增強大型語言模型（LLMs）在醫療問答（QA）中的推理能力和可靠性，減少幻覺的產生。

MedARC的運作包含三個階段：

## 階段一：代理人初始化與獨立答案生成 (Agent Initialization)

1. 初始化代理人群組： 系統初始化一組 N 個自主代理人 $A=\{ A_1​,A_2​,…,A_N \}$。這些代理人可以是基於同一模型或不同模型建立。
2. 2. 獨立生成回應：每個代理人 $A_i$ 根據其預訓練知識與對提示詞（prompt）的理解，獨立地生成初始回應，內容包含答案（$P_i^{(0)}$）、支持論點（$R_i^{(0)}$），以及對自身答案的信心分數（confidence score），作為後續辯論與加權的基礎。



## 階段二：結構化代理人內摘要與多輪討論 (Iterative Refinement)

1. 結構化摘要生成（Structured Summarization）：在每一輪討論後，系統（另一個獨立的語言模型）根據所有代理人的回答，生成一份包含「共識（consensus）」與「分歧（divergence）」的摘要，幫助各代理了解整體討論方向。
2. 多輪辯論式修正（Multi-round Debate & Refinement）：每個代理人根據摘要內容，重新檢視自身的答案與理由，並進行答案、論點以及信心程度的修正。
3. 迭代次數設定：過程重複進行固定輪數 $T$，或直到代理人意見收斂。原作者考慮計算成本，使用固定3輪辯論。最終產生第 $T$ （3）輪的答案集合 $\{P_i^{(T)}\}_{i=1}^N$。


## 階段三：最終答案合成 (Confidence-Aware Aggregation)

1. 收集最終回應：在完成 $T$ 輪討論後，收集每位代理的最終回答 $P_i^{(T)}$ 與對應的信心分數。
2. 信心門檻過濾（Confidence Filtering）：只保留信心分數 ≥ 0.85 的回答；若所有回答皆低於此門檻，系統會重新生成該輪答案並重新評估。
3. 選擇最終答案（Final Selection）：在通過門檻的候選中，**挑選信心分數最高的那一個作為最終答案 $D$**。不採多數決或平均，而以最高信心者為準。
4. 結果輸出：該最終答案即為 MedARC 的輸出結果，並可附帶該代理的論證摘要以供人工檢視。

---

MedARC表現驗證方法
1. 是非題：ACC、precision、recall、F1
2. 事實問答題：[[Recall Oriented Understudy for Gisting Evaluation (ROUGE) score\|ROUGE]]
3. 開放式問題：[[Recall Oriented Understudy for Gisting Evaluation (ROUGE) score\|ROUGE]]、[[SBERT-based Similarity (SBERT-Sim)\|SBERT-Sim]]


---

## 參考文獻

Miao, Y., Wen, J., Luo, Y., & Li, J. (2026). MedARC: Adaptive multi-agent refinement and collaboration for enhanced medical reasoning in large language models. _International Journal of Medical Informatics_, _206_, 106136. [https://doi.org/10.1016/j.ijmedinf.2025.106136](https://doi.org/10.1016/j.ijmedinf.2025.106136)