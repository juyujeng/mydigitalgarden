---
{"dg-publish":true,"permalink":"/My GPTs可以調整的參數/","title":"My GPTs可以調整的參數","tags":["blog","ai","chatgpt"],"created":"2023-11-27","updated":"2023-11-27"}
---


### 可調整的參數包括：

1. **溫度（Temperature）**:
    - 控制生成文本的隨機性和創造性。
    - API的說明文件寫0 ~ 2。數字越少回答越一致，數字越大回答越有創意。
2. **最大輸出長度（Max Tokens）**:
    - 決定模型生成文本的最大長度。
3. **頻率懲罰（Frequency Penalty）**:
    - 降低重複使用已出現單詞的傾向。
    - API的說明文件寫 -2 ~ 2 ，數字越高越不會出現相同的詞。
1. **存在懲罰（Presence Penalty）**:  
    - 鼓勵模型生成新內容。
    - API的說明文件寫 -2 ~ 2 ，數字越高越不會出現已經存在的內容主題。