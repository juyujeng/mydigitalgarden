---
{"dg-publish":true,"permalink":"/@work stuff/self-consistency prompting/","title":"self-consistency prompting","tags":["chatgpt","ai","prompt"],"created":"2024-02-01T10:52","updated":"2024-02-01T14:47"}
---



## 說明

這個技巧由[Wang et al., (2023)](https://arxiv.org/abs/2203.11171)提出。方式是在prompting中提供LLM多種可能的思考方式，讓LLM最後選擇在多種思考方式間，比較一致的答案。

根據[Wang et al., (2023)](https://arxiv.org/abs/2203.11171)的範例，prompting的input要寫很長，才可以涵蓋多種可能的思考方式。如下圖，他們在prompting中寫了多種不同運算方式的數學題作為範例。

![Pasted image 20240201105823.png](/img/user/@work%20stuff/Pasted%20image%2020240201105823.png)

與[[@work stuff/Chain-of-Thought Prompting\|Chain-of-Thought Prompting]] 不同之處在於，self-consistency考慮了多個思考的方式。而在[[@work stuff/Chain-of-Thought Prompting\|Chain-of-Thought Prompting]]則是產生某一個思考方式下最可能的答案。