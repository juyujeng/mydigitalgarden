---
{"dg-publish":true,"permalink":"/Blog/Document/語音轉文字AI工具比較/","title":"語音轉文字AI工具比較","tags":["blog","ai","text"],"created":"2023-03-28T00:00:00.000Z","updated":"2023-03-28T00:00:00.000Z"}
---


# 語音轉文字AI工具比較

近來因為要做會議紀錄的關係開始有了需要進行語音轉文字的需求。我試了兩種AI工具，[雅婷逐字稿](https://asr.yating.tw/)以及[Whisper](https://github.com/openai/whisper)。雅婷逐字稿是臺灣的公司開發的線上工具，需要將影音檔上傳；而[Whisper](https://github.com/openai/whisper)則是openAI公司開發的開源程式，可以單機執行。只是Whisper轉譯的速度實在太慢了，我使用的是它的延伸程式[Whisper.cpp](https://github.com/ggerganov/whisper.cpp)。[Whisper.cpp](https://github.com/ggerganov/whisper.cpp)是用C/C++來運作，比起原來用`python`的[Whisper](https://github.com/openai/whisper)速度快了不少。使用上兩種工具適合的目的不太一樣，雅婷如其名，適合進行逐字稿的繕打，而[Whisper](https://github.com/openai/whisper)較適合用來產生字幕。以下就我的使用情況進行比較

## 雅婷逐字稿

### 優點

1. google meet錄影的音檔，中文有不錯的辨識率。（英文出錯率就挺高的，但我的使用中，英文出現的比例很低）
2. 轉譯速度快，1小時的音檔在15分鐘左右便可以辨識完成
3. 能自動辨識並標示發言者。這個功能在會議紀錄中是很重要的，才能知道誰說了什麼，誰指派了什麼任務
4. 能夠自動把同一個人較長的發言合併在一起
5. 使用方式很簡單。雖然是網頁功能，但使用介面很友善，進行編輯也很簡單
6. 可以自動產生重點摘要。但我在我4次的使用經驗中，它都無法自動產生重點摘要。可能因為會議時間都約1小時，太長。我需要在產生的逐字稿上自己畫重點，雅婷可以幫我整理畫好的重點。
7. 能夠與其他人共用逐字稿，可以共同編輯
8. 能夠匯出多種逐字稿格式（pdf, word, odt, csv, txt, srt）

### 缺點

1. 需要上傳影音檔至雅婷的伺服器，可能有資安或是隱私的疑慮
2. 英文辨識錯誤率高（至少在我目前幾次的使用經驗中）
   - 例如 ChatGPT 很常被辨識為gp。有些時候英文單詞甚至會被忽略。
3. 要錢，需預先購買可以使用的時數

## [Whisper.cpp](https://github.com/ggerganov/whisper.cpp)

### 優點

1. 中文、英文都有不錯的辨識率（英文雖然也不一定辨識對，但音節的長度幾乎都是對的）。
   - 例如 ChatGPT 至少會被辨識為ChedGPT，Bloom taxonomy被辨識為Bloom Tosanomy
2. 轉譯速度快，1小時的音檔在15分鐘左右便可以辨識完成
3. 單機執行，沒有隱私的疑慮
4. 免費
5. 自動形成較短的斷句，適合做字幕
6. 有多種輸出格式（txt, vtt, srt）

### 缺點

1. 使用的技術門檻高，介面不人性
2. 轉譯的速度受限於使用者的硬體設備
3. 不能自動辨識發言者

### 其他

[Whisper](https://github.com/openai/whisper)在開發出來之後，近來已經延伸出許多支援的工具，像是[whisper.cpp](https://github.com/ggerganov/whisper.cpp)以及[WhisperDesktop](https://github.com/Const-me/Whisper)。其中[WhisperDesktop](https://github.com/Const-me/Whisper)已經變成圖形化介面，也支援GPU，對使用者很友善。但是目前只支援windows作業系統。

## 比較表

|             | **雅婷逐字稿**                     | **Whisper.cpp** |
| ----------- | ----------------------------- | --------------- |
| **技術門檻**    | 低                             | 高               |
| **中文辨識率**   | 佳                             | 佳               |
| **轉譯速度**    | 快                             | 快               |
| **價格**      | 100/1小時音檔                     | 免費              |
| **線上/單機執行** | 線上                            | 單機              |
| **輸出格式**    | pdf, word, odt, csv, txt, srt | txt, vtt, srt   |
※若使用原來的 Whisper 轉譯速度很慢，不使用 GPU 的話 10 分鐘的錄音檔就要轉 1 小時。