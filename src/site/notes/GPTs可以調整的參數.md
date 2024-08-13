---
{"dg-publish":true,"permalink":"/GPTs可以調整的參數/","title":"GPTs可以調整的參數","tags":["blog","ai","chatgpt"],"created":"2023-11-27T00:00:00.000Z","updated":"2024-08-13T15:57"}
---


這些參數在API中可以設定，但在MyGPTs當中不能設定。

### 使用API可調整的參數包括：

1. **溫度（Temperature）**:

> What sampling temperature to use, between 0 and 2. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic.
> ==We generally recommend altering this or `top_p` but not both.==

- 控制生成文本的隨機性。數字越少回答越一致，數字越大回答越不可預測。
- 例如在完成「我最喜歡的動物是  。」這個句子時，如果將溫度設定為0，則應該會產生10次都是同樣的句子； 而若是將溫度設定為較高的值產生10次，則會有不同的句子產生。


2. **Top P**：

> An alternative to sampling with temperature, called nucleus sampling, where the model considers the results of the tokens with top_p probability mass. So 0.1 means only the tokens comprising the top 10% probability mass are considered.
> ==We generally recommend altering this or `temperature` but not both.==

3. **最大輸出長度（Max Tokens）**:
		- 在生成文字時GPT模型可以處理的token上限
		- > The maximum number of [tokens](https://platform.openai.com/tokenizer) to generate in the completion.
4. **頻率懲罰（Frequency Penalty）**:
		- 降低重複使用已出現單詞的傾向。
		- API的說明文件寫 -2 ~ 2 。若是正值，則會降低已出現在文本中的字詞的產生機率；若是負值則會增加。
		- > Number between -2.0 and 2.0. Positive values penalize new tokens based on their existing frequency in the text so far, decreasing the model's likelihood to repeat the same line verbatim.
5. **存在懲罰（Presence Penalty）**:
		- 鼓勵模型生成新主題內容。
		- API的說明文件寫 -2 ~ 2 ，數字越高越不會出現已經存在的內容主題。
			- 例如：要GPT產生某款汽車的優點。若設為-2，可能只圍繞著外觀提優點；但若設為2，則會提到各種不同面向的優點。
		- > Number between -2.0 and 2.0. Positive values penalize new tokens based on whether they appear in the text so far, increasing the model's likelihood to talk about new topics.
