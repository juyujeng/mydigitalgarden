---
{"dg-publish":true,"permalink":"/untrained, pretrained, trained model of large language model/","title":"untrained, pretrained, trained model of large language model","tags":["chatgpt","LLMAI"],"created":"2025-02-17T10:11","updated":"2025-02-17T10:25"}
---


大型語言模型（LLM）中常見的 untrained model、pretrained model 和 trained model 指的是不同的訓練階段與用途：

### 1. Untrained Model（未訓練模型）

- 指的是剛初始化的模型，僅具有基本的架構（如 Transformer），但尚未經過任何數據訓練。
- 此時的模型無法進行任何有意義的推理，因為權重參數都是隨機的。
- 例如，若使用 GPT 架構但未經訓練，則它不具備語言理解能力。

### 2. Pretrained Model（預訓練模型）

- 指的是已經在大規模數據集（如網頁文本、書籍、論文等）上進行預訓練（pretraining）的模型。
- 預訓練模型已經學會語言的基本規則、語法結構和常見知識，但尚未針對特定任務進行調整。

### 3. Trained Model（已訓練模型）

- 指的是在預訓練基礎上，經過專門**針對特定任務進行訓練**的模型，例如：
    - 醫學 AI：在醫學文本數據集上微調，使其更適合醫療領域。
    - 法律 AI：在法律案例文本上微調，使其具備法律專業能力。


> [!info] MyGPTs (custom GPT)算是trained model嗎？
> 不算。
> 使用提示（prompt）或指令（instruction）可以引導模型生成特定類型的輸出，但沒有改變模型本身的權重參數，不是訓練新模型。
