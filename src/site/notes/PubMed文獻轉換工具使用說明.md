---
{"dg-publish":true,"permalink":"/PubMed文獻轉換工具使用說明/","title":"PubMed文獻轉換工具使用說明","tags":["ai","LLMAI","python","guideline"],"created":"2025-12-26T16:34","updated":"2025-12-26T16:34"}
---


## 為什麼需要這個工具?

### PubMed資料輸出的困境

當我們在PubMed資料庫搜尋文獻時,經常會遇到一個兩難的問題:

**想要完整的摘要(Abstract)嗎?**

- ✅ 可以!但只能選擇 **TXT純文字格式**
- ❌ 問題是:TXT檔案無法像Excel那樣方便地檢視、篩選或標記重點
- ❌ 所有文獻擠在一個長長的文字檔裡,要找特定資訊非常困難

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

這個Python程式可以將PubMed的TXT格式文獻檔案,轉換成包含完整摘要的CSV試算表格式。

### 轉換前 vs 轉換後

**轉換前(TXT檔案):**

```
1. J Clin Med. 2019 Apr 16;8(4):522. doi: 10.3390/jcm8040522.

Personalized Three-Dimensional Printed Models in Congenital Heart Disease.

Sun Z(1), Lau I(2), Wong YH(3), Yeong CH(4).

Author information:
(1)Discipline of Medical Radiation Sciences...
...
(整篇文獻擠在一起,難以瀏覽)
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

## 程式運作原理

### 簡單來說

這個程式就像一個「智慧型文字解析器」,它會:

1. **讀取**:打開PubMed的TXT文獻檔案
2. **分析**:識別每篇文獻的開始與結束
3. **提取**:從每篇文獻中抓取重要資訊
4. **整理**:將資訊排列成表格格式
5. **輸出**:儲存為CSV檔案

### 提取的資訊包括

程式會自動提取以下13項資訊:

|欄位|說明|範例|
|---|---|---|
|Number|文獻編號|1, 2, 3...|
|Journal|期刊名稱|J Clin Med|
|Year|出版年份|2019|
|Volume|卷數|8|
|Pages|頁碼|522|
|DOI|數位物件識別碼|10.3390/jcm8040522|
|Title|文獻標題|Personalized 3D Printed Models...|
|Authors|作者名單|Sun Z, Lau I, Wong YH...|
|Author_Affiliations|作者單位|Curtin University, Perth...|
|**Abstract**|**摘要(重點!)**|Patient-specific 3D printed models...|
|PMID|PubMed識別碼|30995803|
|PMCID|PMC識別碼|PMC6517984|
|Conflict_of_Interest|利益衝突聲明|Authors declare no conflict...|

---

## 技術細節:程式如何運作

### 第一步:分割文獻

程式使用「正則表達式(Regular Expression)」來識別每篇文獻的開始位置。

**識別規則**:PubMed的每篇文獻都以數字編號開頭,例如 `1.`, `2.`, `3.`

```python
# 用編號分割各篇文獻
articles = re.split(r'\n(?=\d+\.\s)', content)
```

### 第二步:資訊提取

對每篇文獻,程式會尋找特定的「關鍵字」和「格式模式」來提取資訊。

#### 範例1:提取DOI

```python
# 尋找 "doi:" 後面的內容
doi_match = re.search(r'doi:\s*(.+?)(?:\n|$)', article)
```

#### 範例2:提取標題

```python
# 標題通常在兩個空行之間
title_match = re.search(r'\n\n(.+?)\n\n', article)
```

#### 範例3:提取摘要

```python
# 摘要位於作者資訊之後,DOI之前
abstract_match = re.search(r'Author information:.*?\n\n(.+?)(?=\nDOI:|\nPMID:)', article)
```

### 第三步:資料清理

提取的文字可能包含換行符號或多餘空格,程式會進行清理:

```python
# 將多行文字合併為一行,方便在CSV中顯示
data['Abstract'] = abstract_text.replace('\n', ' ')
```

### 第四步:輸出CSV

使用Python的`csv`模組,將整理好的資料寫入CSV檔案:

```python
with open(output_path, 'w', encoding='utf-8-sig') as f:
    writer = csv.DictWriter(f, fieldnames=fieldnames)
    writer.writeheader()  # 寫入欄位標題
    writer.writerows(data)  # 寫入所有資料
```

**編碼選擇**:`utf-8-sig`確保Excel可以正確顯示中文字元。

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

1. 下載程式碼 [convert.py](https://drive.google.com/file/d/1GajIMkiF9OS4UCfSdrOL0K0ENQ_8A6qm/view?usp=sharing)
2. 將PubMed的TXT檔案放在同一個資料夾
3. 修改程式碼中的檔案名稱(第104-105行):
    
    ```python
    input_file = "你的檔案名稱.txt"output_file = "輸出檔案名稱.csv"
    ```
    
4. 開啟命令列視窗,執行:
    
    ```
    python convert.py
    ```
    

#### 方法B:在其他Python程式中呼叫

```python
from convert import convert_pubmed_to_csv

# 自訂檔案名稱
convert_pubmed_to_csv("我的文獻.txt", "結果.csv")
```

#### 方法C:批次處理多個檔案

```python
from convert import convert_pubmed_to_csv

files = [
    ("心血管文獻.txt", "心血管_結果.csv"),
    ("神經科學文獻.txt", "神經科學_結果.csv"),
]

for input_f, output_f in files:
    convert_pubmed_to_csv(input_f, output_f)
```

---

## 常見問題

### Q1:程式顯示「找不到檔案」?

**答**:檢查輸入的檔案名稱是否完全正確,包括副檔名(`.txt`)和大小寫。

### Q2:CSV檔案在Excel中顯示亂碼?

**答**:開啟Excel後,使用「資料」→「從文字/CSV」匯入,並選擇編碼為「UTF-8」。

### Q3:某些文獻的摘要沒有被提取?

**答**:可能是該文獻的格式略有不同。這個程式基於常見的PubMed格式設計,少數特殊格式可能需要手動調整。

### Q4:可以修改提取的欄位嗎?

**答**:可以!在程式碼的第16-29行定義了所有欄位,你可以增加或刪除欄位。

### Q5:能處理多大的檔案?

**答**:理論上沒有限制,但建議單次處理不超過1000篇文獻,以確保效能。
