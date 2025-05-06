---
{"dg-publish":true,"permalink":"/Ensemble Refinement strategy/","title":"Ensemble Refinement strategy","tags":["chatgpt","LLMAI","ai","prompt"],"created":"2025-05-02T16:11","updated":"2025-05-06T10:26"}
---

`Ensemble Refinement`是一種兩階段推理法，結合「多樣性生成」與「答案整合」。具體來說，在第一階段，大型語言模型對同一個問題進行多次[[@work stuff/Chain-of-Thought Prompting\|chain of thought]]推理與作答，產生一組包含不同推理歷程與結果的初步回答。接著進入第二階段，這些生成結果被作為新的提示（prompt），重新輸入模型，讓模型「閱讀自己之前的思考歷程」，並在綜合各版本優缺點後產出一個新的、加強版的答案。重複這個步驟多次，獲得多次第二階段的加強版答案。最終結果為多個加強版答案的 多數決結果。這個方法不像傳統多數決只選答案，而是讓模型主動分析和整合自己的多條推理路徑，類似於「自我審閱與重構」。

與此相比，[[self-consistency strategy\|Self-Consistency]] 則是一種較簡單的策略。其運作方式為多次產生推理結果後，直接根據答案的出現次數進行多數決，選出最常見的答案作為輸出。此方法不需要重新輸入模型整合答案，計算成本較低。

---

### 參考文獻

Singhal, K., Tu, T., Gottweis, J., Sayres, R., Wulczyn, E., Amin, M., Hou, L., Clark, K., Pfohl, S. R., Cole-Lewis, H., Neal, D., Rashid, Q. M., Schaekermann, M., Wang, A., Dash, D., Chen, J. H., Shah, N. H., Lachgar, S., Mansfield, P. A., … Natarajan, V. (2025). Toward expert-level medical question answering with large language models. _Nature Medicine_, _31_(3), 943–950. [https://doi.org/10.1038/s41591-024-03423-7](https://doi.org/10.1038/s41591-024-03423-7)