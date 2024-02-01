---
{"dg-publish":true,"permalink":"/@work stuff/Chain-of-Thought Prompting/","title":"What is Chain-of-Thought Prompting?","tags":["chatgpt","ai","prompt"],"created":"2024-01-15T14:17","updated":"2024-02-01T10:52"}
---


## 說明

Chain-of-Thought (CoT) Prompting 指利用promps引導AI一步一步地產生正確的答案，而不是直接詢問答案。CoT 可以是說明獲得最終答案過程的步驟來引導到最後的答案，或是要求AI一步一步地思考。換言之，就是引導 AI **thinking out loud**，讓它將思考的過程output出來，籍此讓文字的產生引導到最後正確的答案。

這種prompting的方法很適合用來解決複雜任務（如：解數學、邏輯題）。在 CoT 的過程中一步一步地將問題細分為子問題，一步步解決。

## 範例

- 利用`step by step`，讓AI自己一步步地導到最後的答案

> "Explain how to calculate the area of a circle with a radius of 5cm, **==step by step==**."

- 在prompt中詳述步驟或是給予範例

> ![Pasted image 20240201095733.png](/img/user/@work%20stuff/Pasted%20image%2020240201095733.png)
> ([Wei et al., 2022](https://arxiv.org/abs/2201.11903))
