---
{"dg-publish":true,"permalink":"/SBERT-based Similarity (SBERT-Sim)/","title":"SBERT-based Similarity (SBERT-Sim)","tags":["LLMAI","chatgpt","guideline","evaluation","statistics"],"created":"2025-10-21T15:15","updated":"2025-10-23T23:18"}
---


在自然語言處理中，想知道「兩句話是否在講同樣的意思」是一個關鍵問題。例如：「The patient has a fever」與「The patient is running a temperature」雖然用詞不同，但語意幾乎相同。傳統的詞彙重疊方法（如 [[Recall Oriented Understudy for Gisting Evaluation (ROUGE) score\|ROUGE]]）無法很好地捕捉這種語意等價，因此研究者開發了 **Sentence-BERT（SBERT）**。它可以把每個句子轉換成一個「語意向量」，並用餘弦相似度（cosine similarity）衡量兩句話的語意接近程度（Reimers & Gurevych, 2019）。

## 一、SBERT 的原理

BERT 模型能理解語言，但每次比較兩個句子時都要「同時輸入」它們，這樣計算量非常大（比較 10,000 句話要花 65 小時）。 SBERT 解決了這個問題，讓每個句子能先被轉換成一個固定長度的**語意向量（embedding）**。 這樣，系統只需比較向量之間的距離就能知道語意相似度。

這個設計稱為「**Siamese Network（孿生網路結構）**」：

- 兩個句子分別進入相同的 BERT 模型（權重共享），
- 產生兩個向量（u 和 v），
- 然後用數學方法比較它們的距離或角度。

這種方式就像是把句子放進同一張「語意地圖」上：
距離越近，意思越接近。

## 二、計算方式

SBERT 最常用的比較方法是**餘弦相似度（cosine similarity）**：

$\text{similarity} = \frac{u \cdot v}{||u|| \times ||v||}$

- 當兩個向量方向幾乎一樣（語意相似）時，值接近 **1**；
- 當方向相反（語意相反）時，值接近 **-1**；
- 若完全無關，值約為 **0**。

舉例來說：

- 「Dogs are friendly」 vs. 「Cats are friendly」 → 相似度 ≈ 0.85
- 「Dogs are friendly」 vs. 「The sky is blue」 → 相似度 ≈ 0.10

這表示前者語意相近，後者語意無關。

## 三、結果的意義

SBERT-Sim 的輸出是一個介於 -1 到 1 之間的數字：

- 越接近 1 → 兩句話語意越接近；
- 約為 0 → 幾乎沒有語意關聯；
- 越接近 -1 → 意思相反（例如「The door is open」vs「The door is closed」）。

這個指標特別適合：

- 測量問答或摘要中「語意是否一致」；
- 找出資料庫中「意思最接近」的句子；
- 測量大型語言模型（LLM）生成回應與標準答案的語意相似性。

## 四、Python 範例

以下展示如何用 `sentence-transformers` 套件計算 SBERT 語意相似度：

```python
# 安裝套件
# pip install sentence-transformers

from sentence_transformers import SentenceTransformer, util

# 載入 SBERT 模型（輕量且常用的版本）
# model = SentenceTransformer('all-MiniLM-L6-v2')

# 處理中文的模型
# model_name = "shibing624/text2vec-base-chinese"
model_name = "sentence-transformers/distiluse-base-multilingual-cased-v1" 
model = SentenceTransformer(model_name) # device (like “cuda”, “cpu”, “mps”, “npu”) that should be used for computation. If None, checks if a GPU can be used.

# 兩個要比較的句子
sent1 = "這位病人出現發燒、頭痛與咳嗽的症狀。"
sent2 = "患者有發燒且頭痛，並伴有咳嗽。"

# 將句子轉為向量
emb1 = model.encode(sent1, convert_to_tensor=True)
emb2 = model.encode(sent2, convert_to_tensor=True)
 

# 計算餘弦相似度

cos_sim = util.pytorch_cos_sim(emb1, emb2).item()
cos_sim
```

> [!NOTE] 處理中文的模型選擇
>
> - 到huggingface的[頁面](https://huggingface.co/models)中篩選
> 	- Task: Natural language processing/sentence similarity
> 	- Libraries: sentence-transformers
> 	- Languages: Chinese
> - 模型眾多，務必選擇針對「sentence similarity」進行微調的模型，如此轉換成向量計算的cos才有相似性的意義。

---

## Reference

Reimers, N., & Gurevych, I. (2019). Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks. *Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP)*, 3980–3990. <https://doi.org/10.18653/v1/D19-1410>
