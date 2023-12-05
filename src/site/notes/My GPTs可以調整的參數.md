---
{"dg-publish":true,"permalink":"/My GPTs可以調整的參數/","title":"My GPTs可以調整的參數","tags":["blog","ai","chatgpt"],"created":"2023-11-27T00:00:00.000Z","updated":"2023-12-05T00:00:00.000Z"}
---


### 可調整的參數包括：

20231205: 這些參數在API中可以設定，但似乎在MyGPTs當中不能設定…

1. **溫度（Temperature）**:
   - 控制生成文本的隨機性。
   - API的說明文件寫0 ~ 1。數字越少回答越一致，數字越大回答越不可預測。
   - 例如在完成「我最喜歡的動物是  。」這個句子時，如果將溫度設定為0，則應該會產生10次都是同樣的句子； 而若是將溫度設定為較高的值產生10次，則會有不同的句子產生。
   - > The sampling temperature, between 0 and 1. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic. If set to 0, the model will use [log probability](https://en.wikipedia.org/wiki/Log_probability) to automatically increase the temperature until certain thresholds are hit.
2. **最大輸出長度（Max Tokens）**:
   - 在生成文字時GPT模型可以處理的token上限
   - > The maximum number of [tokens](https://platform.openai.com/tokenizer) to generate in the completion.
3. **頻率懲罰（Frequency Penalty）**:
   - 降低重複使用已出現單詞的傾向。
   - API的說明文件寫 -2 ~ 2 。若是正值，則會降低已出現在文本中的字詞的產生機率；若是負值則會增加。
4. **存在懲罰（Presence Penalty）**:
   - 鼓勵模型生成新主題內容。
   - API的說明文件寫 -2 ~ 2 ，數字越高越不會出現已經存在的內容主題。
