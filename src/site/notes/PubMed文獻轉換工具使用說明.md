---
{"dg-publish":true,"permalink":"/PubMed文獻轉換工具使用說明/","title":"PubMed文獻轉換工具使用說明","tags":["ai","LLMAI","python","guideline"],"created":"2025-12-26T16:34","updated":"2025-12-26T16:34"}
---


## 為什麼需要這個工具?

### PubMed資料輸出的困境

當我們在PubMed資料庫搜尋文獻時,經常會遇到一個兩難的問題:

**想要完整的摘要(Abstract)嗎?**

- ✅ 可以!PubMed提供多種包含摘要的格式
	- ❌ 問題是:這些格式(如TXT、NBIB)都是純文字檔案,無法像Excel那樣方便地檢視、篩選或標記重點
	- ❌ 所有文獻擠在一個長長的文字檔裡,要找特定資訊非常困難
	- ❌ 即使是結構化的NBIB格式,也不易於閱讀和管理

**想要方便管理的試算表格式?**

- ✅ 可以!PubMed可以輸出為 **CSV格式**
	- ❌ 問題是:預設的CSV輸出**不包含摘要(Abstract)**
	- ❌ 失去了摘要,就很難快速判斷文獻是否符合需求

這就像是:

- 要嘛選擇「內容完整但難以閱讀」的筆記本
- 要嘛選擇「方便整理但內容不全」的表格

**我們能否兩者兼得?** 這就是這個工具誕生的原因!

---
## 這個工具能做什麼?

這個Python程式可以將PubMed的NBIB格式文獻檔案,轉換成包含完整摘要的CSV試算表格式。

### 為什麼選擇NBIB格式?

NBIB (National Library of Medicine Bibliographic format) 是PubMed的標準書目格式,具有以下優勢:

1. **結構化標籤**: 每個欄位都有明確的標籤識別(如 `TI -` 代表標題)
2. **內容完整**: 包含所有文獻資訊,包括完整摘要
3. **格式穩定**: 標準化格式,解析準確度高

### 轉換前 vs 轉換後

**轉換前(.nbib檔案):**

```
PMID- 29793717
TI  - Quality assurance processes for standardized patient programs.
AB  - OUR PROBLEM: As the pharmacy profession evolves to include non-dispensing 
      services and collaborative care, greater emphasis is placed on communication 
      skills building through standardized patient programs...
AU  - Zhang S
AU  - Soreide KK
...
(標籤式格式,難以快速瀏覽比較)
```

**轉換後(CSV檔案,可用Excel開啟):**

|Number|Journal|Year|Title|Authors|Abstract|PMID|DOI|
|---|---|---|---|---|---|---|---|
|1|J Clin Med|2019|Personalized 3D...|Sun Z, Lau I...|Patient-specific...|30995803|10.3390/...|
|2|...|...|...|...|...|...|...|

現在你可以:

- ✅ 在Excel中輕鬆瀏覽所有文獻
- ✅ 使用篩選功能快速找到特定主題
- ✅ 標記重要文獻、加上註解
- ✅ 完整保留所有摘要內容
- ✅ 依需求排序、分類

---

## 如何從PubMed下載NBIB格式檔案?

### 步驟說明

1. **在PubMed搜尋文獻**
    - 前往 [PubMed](https://pubmed.ncbi.nlm.nih.gov/)
    - 輸入你的搜尋關鍵字
2. **選擇要下載的文獻**
    - 可以選擇特定文獻,或全選所有搜尋結果
    - 點選文獻旁的核取方塊
3. **下載NBIB格式**
    - 點選頁面上方的 **"Send to"** 按鈕
    - 選擇 **"Citation manager"**
4. **檔案說明**
    - 下載的檔案副檔名為 `.nbib`
    - 這是純文字檔案,可用任何文字編輯器開啟
    - 包含完整的文獻資訊,包括摘要


## 程式運作原理

### 簡單來說

這個程式就像一個「智慧型文字解析器」,它會:

1. **讀取**:打開PubMed的`.nbib`文獻檔案
2. **分析**:識別每篇文獻的開始與結束
3. **提取**:從每篇文獻中抓取重要資訊
4. **整理**:將資訊排列成表格格式
5. **輸出**:儲存為CSV檔案

### 提取的資訊包括

程式會自動提取以下13項資訊:
NBIB使用標準化的標籤來標記不同類型的資訊:

|標籤|意義|範例|
|---|---|---|
|PMID-|PubMed唯一識別碼|29793717|
|TI -|標題 (Title)|Quality assurance processes...|
|AB -|摘要 (Abstract)|OUR PROBLEM: As the pharmacy...|
|AU -|作者 (Author)|Zhang S|
|AD -|作者單位 (Affiliation)|University of Michigan...|
|TA -|期刊簡稱 (Journal)|Curr Pharm Teach Learn|
|DP -|出版日期|2018 Apr|
|VI -|卷數 (Volume)|10|
|IP -|期數 (Issue)|4|
|PG -|頁碼 (Pages)|523-528|
|PT -|出版類型|Journal Article; Review|
|OT -|關鍵字 (Keywords)|Assessment; Communication|
|LA -|語言|eng|

---

## 使用方法

### 前置準備

1. **安裝Python**:從 [python.org](https://www.python.org/downloads/) 下載安裝
2. **準備PubMed文獻檔案**:
    - 在PubMed搜尋文獻
    - 選擇要下載的文獻
    - 選擇格式:`Send to` → `File` → 格式選 `PubMed`
    - 儲存為TXT檔案

### 執行步驟

#### 方法A:直接執行(最簡單)

1. 將[程式碼](https://drive.google.com/file/d/1GajIMkiF9OS4UCfSdrOL0K0ENQ_8A6qm/view?usp=sharing)儲存為 `converter.py`
2. 將NBIB檔案放在同一個資料夾
3. 修改程式碼中的檔案名稱(第160-161行):

```
input_file = "你的檔案名稱.nbib"
output_file = "輸出檔案名稱.csv"
```

4. 開啟命令列視窗,執行:

```
python nbib_converter.py
```

#### 方法B:在其他Python程式中呼叫

```
from convert import convert_nbib_to_csv

# 自訂檔案名稱
convert_nbib_to_csv("我的文獻.nbib", "結果.csv")
```

#### 方法C:批次處理多個檔案

```
from nbib_converter import convert_nbib_to_csv

files = [
    ("心血管文獻.nbib", "心血管_結果.csv"),
    ("神經科學文獻.nbib", "神經科學_結果.csv"),
    ("腫瘤學文獻.nbib", "腫瘤學_結果.csv"),
]

for input_f, output_f in files:
    print(f"\n處理: {input_f}")
    convert_nbib_to_csv(input_f, output_f)

```