---
{"dg-publish":true,"permalink":"/rouge-chinese/","title":"rouge-chiese","tags":["python","nlp","guideline"],"created":"2025-10-22T10:56","updated":"2025-10-24T22:43"}
---


url: <https://pypi.org/project/rouge-chinese/1.0.1/?utm_source=chatgpt.com>

## 使用注意事項

- 需要先利用先將中文句子進行「斷詞」（word segmentation）處理，分隔不同的字詞，才有辦法進行後續的[[Recall Oriented Understudy for Gisting Evaluation (ROUGE) score\|ROUGE]]分數計算。
- 若未先斷詞，`rouge-chinese` 會把整句當作一連串字元計算，導致分數嚴重偏低。
- 常見的套件包含
	- [`ckip-transformers`](https://github.com/ckiplab/ckip-transformers)：由中研院開發的繁體中文 NLP 模型套件，對臺灣繁體中文的分詞較準確。
	- [`jieba`](https://github.com/fxsjy/jieba)：基於詞典與統計規則的中文分詞工具，輕量、速度快。

## 使用[`ckip-transformers`](https://github.com/ckiplab/ckip-transformers)

> [!Attention] 進行斷詞的物件務必是list，而非string

```{python}
from ckip_transformers.nlp import CkipWordSegmenter
from rouge_chinese import Rouge

# 初始化 CKIP 斷詞模型（建議明確指定 model）
ws_driver = CkipWordSegmenter(model="albert-base") # 或bert-base

# 待處理句子（一定要以 list 形式輸入）
hypothesis = ["病人有發燒且頭痛，並伴隨咳嗽。"]
reference = ["這位病人出現發燒、頭痛與咳嗽的症狀。"]

# 進行斷詞
ws_h = ws_driver(hypothesis)
ws_r = ws_driver(reference)

# 將詞組合回字串，以空格分隔
hypothesis_seg = ' '.join(ws_h[0])
reference_seg = ' '.join(ws_r[0])

# 計算 ROUGE 分數
rouge = Rouge()
scores = rouge.get_scores(hypothesis_seg, reference_seg)
print(scores)

```

## 使用jieba

```{python}
from rouge_chinese import Rouge
import jieba # you can use any other word cutting library

hypothesis = "病人有發燒且頭痛，並伴隨咳嗽。" # '病人 有 發燒且 頭痛 ， 並伴 隨 咳嗽 。'
hypothesis = ' '.join(jieba.cut(hypothesis)) 

reference = "這位病人出現發燒、頭痛與咳嗽的症狀。"
reference = ' '.join(jieba.cut(reference)) # '這位 病人 出現 發燒 、 頭痛 與 咳嗽 的 症狀 。'

rouge = Rouge()
scores = rouge.get_scores(hypothesis, reference)

```
