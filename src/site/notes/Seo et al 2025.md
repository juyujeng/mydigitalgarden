---
{"dg-publish":true,"permalink":"/Seo et al 2025/","title":"Large Language Models as Evaluators in Education: Verification of Feedback Consistency and Accuracy","tags":["LLMAI","guideline","education","virtual-teacher","chatgpt"],"created":"2026-03-16T10:56","updated":"2026-03-16T10:56"}
---

   

## 方法與結果

本研究目的為驗證大型語言模型（LLMs）作為教育領域「自動化評估者（LLMs-as-evaluators）」的可靠性與一致性。研究團隊使用 MCTest 資料集模擬智慧家教系統中的師生互動，先由三個模型（GPT-4o、Claude-3、Llama-3.1-70B）針對學生的錯誤回答產出教學回饋，並對比了「包含」與「不包含」評分回饋標準的提示詞策略。
隨後，研究採用五個不同的 LLM（GPT-4o、Llama 家族與 Gemma 家族模型）對生成的教學回饋進行評分（詳見[[Seo et al 2025#對回饋的評分標準\|#對回饋的評分標準]]），評分系統採用二元量表（符合給 1 分，否則給 0 分），標準涵蓋：正確性（Correct）、不洩漏答案（Revealing）、引導性（Guidance）、診斷性（Diagnostic）與鼓勵性（Encouragement）五大維度。最後，研究透過測量單一模型多次評分的「內部一致性」、不同模型間的「模型間一致性」，並將結果與人類專家的評分進行準確率比對，以全面分析 LLM 的評分效能。

研究結果顯示，LLM 在「正確性」與「不洩漏答案」上展現出極高的內部與模型間一致性，且與人類專家的評分高度吻合。然而，對於「診斷性」與「鼓勵性」等較為主觀且複雜的標準，不僅人類專家之間難以達成共識，LLM 的穩定性與準確率也顯著下降，甚至在給予相同提示詞時仍會產生不一致的評估結果。
此外，評分結果的變異性深受提示詞策略與模型架構的影響；例如，當提示詞未提供對回饋的評分標準時，LLM 容易盲目給出高分，而在模型架構上，Gemma 家族模型展現出比 Llama 家族更為集中的穩定評分分佈。研究亦指出，增加回饋的句子數量對整體評估分數的影響微乎其微。總結而言，儘管 LLM 深具作為教育評估工具的潛力，但在面對複雜的教學指標時仍具挑戰，實務應用上必須謹慎選擇模型組合與優化提示詞，以確保評分的可靠性。

## 結論

LLMs 在自動化教育評估中展現了巨大潛力，特別是在處理客觀性強的評估任務時。然而，要將其作為可靠的教育評估工具，必須注意以下幾點：

- **謹慎選擇準則:** 在處理涉及診斷性與情感語氣的複雜教育指標時，單一 LLM 的評估結果不可完全信賴。
- **組合評估模型:** 建議採用多模型組合（Ensemble）及多數決機制來提高評估的客觀性與穩定性。
- **最佳化評估尺度:** 未來研究應致力於解決 5 點量尺在 LLM 評估中出現的極端化分佈問題，目前二元評估（0 或 1）能提供更高的一致性。
- **特定情境優化:** 針對不同教育背景（如數學、編程、寫作）定制化提示詞與準則，是提升 LLM 評估準確性的關鍵方向。

---


## 對回饋的評分標準

**五大教育評量標準（Binary Scoring）** 有別於傳統的 5 分制，該研究採用**二元評分（符合給 1 分，不符合給 0 分）**，以減少 AI 評分時在中間分數上的搖擺不定

- Correct (COR.): The teacher’s feedback is expected to contain no incorrect statements and to be relevant to the current question and the student’s response.
- Revealing (REV.): The teacher’s feedback should not directly reveal the correct answer to the student.
- Guidance (GUI.): The teacher’s feedback should provide guidance that helps the student move towards the correct answer.
- Diagnostic (DIA.): The teacher’s feedback should accurately identify and address any misunderstandings or errors in the student’s response.
- Encouragement (ENC.): The teacher’s feedback should maintain a positive or encouraging tone.
---

## reference

Seo, H., Hwang, T., Jung, J., Kang, H., Namgoong, H., Lee, Y., & Jung, S. (2025). Large Language Models as Evaluators in Education: Verification of Feedback Consistency and Accuracy. _Applied Sciences_, _15_(2), 671. [https://doi.org/10.3390/app15020671](https://doi.org/10.3390/app15020671)