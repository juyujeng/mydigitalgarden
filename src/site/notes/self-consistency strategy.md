---
{"dg-publish":true,"permalink":"/self-consistency strategy/","title":"self-consistency strategy","tags":["chatgpt","ai","LLMAI"],"created":"2025-05-02T15:23","updated":"2025-05-06T10:27"}
---


在大型語言模型研究中，`self-consistency` 指透過多次抽樣模型的推理路徑，並對其最終答案進行多數決，選擇出最一致的結果，從而提高答案的穩定性與可靠性。此策略不僅保留了推理過程的多樣性，也透過答案的一致性反映出模型對該問題的「內部自信度」。 (Wang, 2023)。

Wang et al. (2023) 提出此策略並應用於數學與邏輯推理任務，顯示可將標準 chain-of-thought 的準確率提升 10–20%。緊接著，Singhal et al. (2023) 將 self-consistency 應用於醫學問答領域，發現Flan-PaLM 模型在 MedQA（USMLE 題型）上表現由 60.6% 提升至 67.6%。更進一步地，Singhal等人讓模型在回答問題時若對某個問題的答案沒有把握，可以選擇不回答，而不是硬著頭皮猜一個答案。這樣的機制讓模型只針對它「比較有信心」的問題作答，避免產生可能錯誤的輸出。這種方法稱為選擇性預測（selective prediction）。在使用這個策略時，研究者觀察模型在多次推理過程中產生的答案是否一致。如果同一個答案多次出現，代表模型對這個答案較有信心；若每次都產生不同答案，則表示模型沒有把握。透過這樣的設計，即使模型放棄回答約 45% 的問題，但在保留下來的回答中，準確率提升至 82.5%。這顯示這種方法不僅能提升模型的可靠度，也能增加使用上的安全性，特別適合應用在醫療等高風險的領域。

---

### 參考文獻

Wang, X., Wei, J., Schuurmans, D., Le, Q., Chi, E., Narang, S., Chowdhery, A., & Zhou, D. (2023). _Self-Consistency Improves Chain of Thought Reasoning in Language Models_ (No. arXiv:2203.11171). arXiv. [https://doi.org/10.48550/arXiv.2203.11171](https://doi.org/10.48550/arXiv.2203.11171)

Singhal, K., Azizi, S., Tu, T., Mahdavi, S. S., Wei, J., Chung, H. W., Scales, N., Tanwani, A., Cole-Lewis, H., Pfohl, S., Payne, P., Seneviratne, M., Gamble, P., Kelly, C., Babiker, A., Schärli, N., Chowdhery, A., Mansfield, P., Demner-Fushman, D., … Natarajan, V. (2023). Large language models encode clinical knowledge. _Nature_, _620_(7972), 172–180. [https://doi.org/10.1038/s41586-023-06291-2](https://doi.org/10.1038/s41586-023-06291-2)