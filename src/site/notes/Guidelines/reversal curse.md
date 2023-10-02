---
{"dg-publish":true,"permalink":"/Guidelines/reversal curse/","title":"reversal curse","tags":["ai","chatgpt","terms","guideline"],"created":"2023-10-02","updated":"2023-10-02"}
---


# reversal curse

reversal curse是大型語言模型的限制之一。它指的是當該模型在訓練時所用的材料多是以「A是B」的形式進行訓練時，模型沒辦法學會「B是A」這種說法。
例如訓練的材料大多描述「蕭茲是現任德國第9任總理」。那麼當詢問該模型「蕭茲是誰？」便有很高的機率能夠獲得答案：「德國總理」。但如果反過來問「現在德國總理是誰？」卻不一定能夠獲得正確的答案。
這樣子的限制會大大影響大型語言模型在演繹推理、資訊搜尋的使用。在詢問ChatGPT得不到想要的答案時，也許要試著重新包裝問題，或許才能找到符合模型訓練資料的形式。

## reference
 	
https://doi.org/10.48550/arXiv.2309.12288