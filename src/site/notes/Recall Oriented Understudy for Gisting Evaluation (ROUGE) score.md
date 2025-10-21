---
{"dg-publish":true,"permalink":"/Recall Oriented Understudy for Gisting Evaluation (ROUGE) score/","title":"Oriented Understudy for Gisting Evaluation (ROUGE) score","tags":["LLMAI","chatgpt","guideline","statistics","evaluation"],"created":"2025-10-21T15:15","updated":"2025-10-21T15:44"}
---

# 了解 ROUGE：自動評估文字摘要品質的指標

在人工智慧與自然語言處理領域，ROUGE（Recall-Oriented Understudy for Gisting Evaluation）是一種常用來衡量「自動產生文字摘要或回答」與「人工標準答案」之間相似度的評估方法（Lin, 2004）。

## 一、ROUGE 的核心概念

ROUGE 的基本想法很簡單：
> 如果一個電腦生成的摘要中，出現了越多與人工摘要中相同的字詞或句子片段，那麼它的品質就越好。

也就是說，ROUGE 用來衡量「自動摘要覆蓋了多少人工摘要中的重要內容」。

ROUGE 系列指標包含多種版本：
- ROUGE-N：比較 n 個連續字詞（n-gram）的重疊數。
- ROUGE-L：使用最長共同子序列（Longest Common Subsequence, LCS）。
- ROUGE-S：計算跳躍式的詞對（skip-bigrams）。
- ROUGE-W：在 LCS 上加入連續字詞的加權版本。

在實際應用中，最常使用的版本是 ROUGE-1、ROUGE-2 和 ROUGE-L。

## 二、ROUGE 的計算方式

在理解 ROUGE 之前，先要知道什麼是「n-gram」。

### 什麼是 n-gram？

n-gram 是一種把句子切成「連續字詞片段」的方式。  
- 當 n = 1 時，稱為「unigram」，也就是單一字或詞。  
  例如：「The cat sat」 → [The]、[cat]、[sat]  
- 當 n = 2 時，稱為「bigram」，即連續兩個詞。  
  例如：「The cat sat」 → [The cat]、[cat sat]  
- 當 n = 3 時，稱為「trigram」，即連續三個詞。  
  例如：「The cat sat」 → [The cat sat]

在 ROUGE-N 中，系統會比較「模型生成摘要」與「人工摘要」之間，這些 n-gram 的重疊程度。  
如果兩段文字共享越多相同的 n-gram，代表語意越接近。

### 計算公式

以最常見的 ROUGE-N 為例，它的公式如下：

$$
\text{ROUGE-N} = \frac{\text{重疊的 n-gram 數}}{\text{參考摘要中的 n-gram 總數}}
$$

這其實就是一種「召回率」（recall），指在所有正確答案元素裡，你找回了多少元素：
- 分子：模型生成摘要中，有多少 n-gram 也出現在人工摘要中。
- 分母：人工摘要中所有的 n-gram。

### 範例

| 類別 | 內容 |
|------|------|
| 參考摘要 | "Cats sit on mats and purr." |
| 模型摘要 | "Cats sit and sleep on mats." |

在這個例子中，人工摘要共有 6 個單字（cats, sit, on, mats, and, purr）。  
模型摘要有 6 個單字，但其中只有 4 個（cats, sit, on, mats）出現在參考摘要裡。

所以：

$$\text{ROUGE-1} = \frac{4}{6} = 0.67$$

意思是模型「召回」了人工摘要中約 67% 的內容。

## 三、結果的意義

ROUGE 的結果通常介於 0 到 1：
- 1.0 代表生成摘要與參考摘要完全一致；
- 0.0 代表完全沒有重疊。


## 四、ROUGE 的 Python 範例

以下示範如何使用 Python 的 `rouge_score` 套件，計算兩段文字的 ROUGE 分數：

```python
# 安裝套件
# pip install rouge-score

from rouge_score import rouge_scorer

# 建立 ROUGE 計算器
scorer = rouge_scorer.RougeScorer(['rouge1', 'rouge2', 'rougeL'], use_stemmer=True)

# 參考摘要與生成摘要
reference = "The cat sat on the mat."
candidate = "The cat is on the mat."

# 計算分數
scores = scorer.score(reference, candidate)

# 顯示結果
for metric, result in scores.items():
    print(f"{metric}: Precision={result.precision:.3f}, Recall={result.recall:.3f}, F1={result.fmeasure:.3f}")
```

### `rouge_score`說明

當我們使用 `rouge_score` 套件計算 ROUGE 時，它會輸出三個數值：**Precision**、**Recall** 和 **F1**。

### 一、Precision

Precision 表示：
> 在AI模型產生的內容中，有多少部分是正確的？

它的計算方式是：

$$\text{Precision} = \frac{\text{重疊的字詞數}}{\text{AI模型摘要的字詞總數}}$$


例如：
- AI模型摘要產生了 10 個字詞，
- 其中有 6 個與人工摘要相同，  
→ Precision = 6 / 10 = 0.6  

這代表模型說的內容中，有 60% 是「正確、出現在人工摘要中的」。

---

### 二、Recall

Recall 表示：
> AI模型有多完整地涵蓋了人工摘要的內容？

它的計算方式是：

$$\text{Recall} = \frac{\text{重疊的字詞數}}{\text{人工摘要的字詞總數}}$$


例如：
- 人工摘要共有 8 個字詞，
- AI模型的回答中有 6 個與它重疊，  
→ Recall = 6 / 8 = 0.75  

這代表模型「涵蓋了」人工摘要中 75% 的重點。

---

### 三、F1

Precision 和 Recall 常常有取捨關係：
- 如果AI模型產生的內容太多，可能 Recall 高但 Precision 低（涵蓋多但不夠準）。
- 如果AI模型產生的內容太少，可能 Precision 高但 Recall 低（很準但不完整）。

因此 F1 分數用來平衡兩者：


$$\text{F1} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$$


F1 越高，表示模型在「準確性」與「完整性」之間取得更好的平衡。

---

### 四、綜合理解與例子

| 指標        | 問題           | 理解方式 | 目標   |
| --------- | ------------ | ---- | ---- |
| Precision | AI說的內容有多精準？  | 準不準  | 越高越好 |
| Recall    | AI有多完整地說出重點？ | 全不全  | 越高越好 |
| F1        | 準確與完整的平均表現   | 綜合分數 | 越高越好 |

假設AI模型回答「The cat on the mat」 
而人工摘要是「The cat sat on the mat」：

- 重疊詞：the, cat, on, mat（4 個）
- 模型共 5 個字，人工共 6 個字  
→ Precision = 4/5 = 0.8  
→ Recall = 4/6 = 0.67  
→ F1 = 2 × (0.8 × 0.67) / (0.8 + 0.67) ≈ 0.73



---

## reference

Lin, C.-Y. (2004). ROUGE: a package for automatic evaluation of summaries. _Text Summarization Branches Out_, 74–81. [https://aclanthology.org/W04-1013/](https://aclanthology.org/W04-1013/)