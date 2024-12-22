---
{"dg-publish":true,"permalink":"/Blog/Document/Whisper.cpp/","title":"Whisper.cpp操作心得","tags":["ai","guideline","research","method"],"created":"2024-06-14T14:20","updated":"2024-12-22T16:53"}
---


[Whisper](https://github.com/openai/whisper)則是openAI公司開發的開源程式，可以單機執行語音轉文字。只是Whisper轉譯的速度實在太慢了，開發者利用C/C++將其編寫成[Whisper.cpp](https://github.com/ggerganov/whisper.cpp)，比起原來用`python`的[Whisper](https://github.com/openai/whisper)速度快了不少。但無論是[Whisper](https://github.com/openai/whisper)或是[Whisper.cpp](https://github.com/ggerganov/whisper.cpp)都是命令列介面（command line interface），使用者需要撰寫程式碼。

> [!NOTE] 一般使用者福音
> 在windows作業系統中，已有使用者開發出[WhisperDesktop](https://github.com/Const-me/Whisper)。是圖形化介面的Whisper，也支援GPU，對使用者很友善。

# Whisper.cpp安裝與更新

兩種安裝方式：

1. 依照[Whisper.cpp](https://github.com/ggerganov/whisper.cpp)的[github網頁](https://github.com/ggerganov/whisper.cpp)依步驟進行。
		1. 要進行更新，只需要在whisper.cc的資料夾中執行終端機，輸入`git pull`便會進行更新
2. 使用`Homebrew`進行安裝。[詳見此](https://formulae.brew.sh/formula/whisper-cpp)。
		- 這個方式安裝上比較簡易，但版本會比github網頁還要慢一點更新。

# Whisper.cpp使用

## 支援的音檔格式

目前Whisper.cpp僅支援16-bit wav檔案，若非該格式則需要先經過轉檔。推薦使用[Audacity](https://www.audacityteam.org/)軟體進行轉檔。

## Whisper.cpp操作範例

### 單檔案轉譯

```
./main -m ./models/ggml-large-v3.bin -f "filepath" -l en --output-vtt
```

- `./main`：利用github安裝後呼叫Whisper.cpp的方法。若是使用Homebrew安裝的話語法完全不一樣。
- `-f`：設定要轉譯的檔案路徑
- `-m`：調整使用的模型。預設是`base`，這個範例中改用`large-v3`
- `-l`：轉譯的語言，這裡是英文（`en`）。若音檔是中文，則要用`zh`。若選擇`auto`則進行自動偵測
- `--output-vtt`：輸出為vtt檔，另可選擇`txt`、`srt`、`lrc`等格式。

### 多檔案轉譯

```
`for i in data/*.wav; do ./main -m ./models/ggml-large-v3.bin -l zh --output-txt -f "$i"; done`
```

- 利用`for`迴圈轉譯「output資料夾」當中所有的wav檔案。
- `-f`：輸入的wav檔案路徑

# 使用心得

利用Whisper.cc轉譯了PEDro scale評分教學影片，共9個英文影片。對英文的轉譯幾乎百分之百正確。在M1的Macbook pro上，5分鐘的音檔5分鐘內就轉譯完成了，很快！

# 附錄

- [進階參數](https://github.com/ggerganov/whisper.cpp/pull/291)
	- Entropy-based threshold support：如果句子有太多的重複可以調整這個參數。數字越小越多重複（預設為2.4）
