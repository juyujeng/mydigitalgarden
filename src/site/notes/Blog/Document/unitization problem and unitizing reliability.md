---
{"dg-publish":true,"permalink":"/Blog/Document/unitization problem and unitizing reliability/","title":"unitization problem and code reliability","tags":["docs","coding","reliability","agreement","method"]}
---


## unitization problem 

在進行文本的分析時通常需要先將文本轉編為可以分析的單位，而要如何決定文本當中的那一個段落是值得分析的過程就是unitization。以Empathic Communication Coding System (ECCS)的分析為例。如何決定哪一個溝通的橋段出現同理的時機，值得進一步去分析治療師同理回應能力就是unitization。

但是當有兩個以上的coders進行文本分析時，很有可能出現這些coders對同一個文本所辨識出來的分析單位（unit）對不上的情況，這就是一種unitization problem造成的後果。

有些文本的分析是直接以時間或是段落為單位，例如整段錄音（影）每30秒為一個單位，判斷這個單位內有沒有出現目標的行為。這種情況下就沒有什麼unitization problem。但有些文本的分析是以unit of meaning  (Campbell et a., 2013）為單位，也就是要先事先定義好某些特定的目標，有出現才將該段落納入分析，像ECCS就是這樣子的例子。

那要怎麼解決不同的coders找到不同的units呢？Campbell等人（2013）提出一個方法，那就是讓研究的主持人（通常是對於該主題最瞭解的人）做為主要unit辨別者，其他的coders只在主持人所找到的units當中進行資料的分析以及分類。這樣子就只會有分類上的歧異，而不會有unitization problem。但大家都知道，主持人很忙，所以最少也要讓主持人主導訓練coders的任務，並且在分類規則上多加參與，以盡量減少unitization problem。

## reliability of unitizing 

目前針對unitization的過程進行信度或是一致性的指標似乎只有Guetzkow's U。其他分類一致性的指標我覺得指標的目的都不全然符合。因為文本當中可能有一大堆片段都沒有被挑出來，這樣可以衝出許多不同coders都一致認為不算meaningful unit的資料點。因此只能從所有的coders都挑出來的units當中去計算信度。但這樣子畫出來的2 by 2  contingency table又會缺少雙方都認為不是的那一格。

### Guetzkow's U

Guetzkow's U則是針對已經找到的units數量上來計算兩個coders所找到的數量上是否一致。其公式如下：

$$U = \frac{O_1 - O_2}{O_1 + O_2}$$

其中$O_1$代表第一個coder找到的所有units數量，而$O_2$則是第二位coder找到的units數量。

這個方法假設，如果兩個coders的能力是相同的，那麼雙方找到的units數量的期望值應該會是相同的（為常數$h$）。

因此，$U$越接近0，應該兩個coders的unitizing越一致。

---

## references

Campbell, J. L., Quincy, C., Osserman, J., & Pedersen, O. K. (2013). Coding In-depth Semistructured Interviews: Problems of Unitization and Intercoder Reliability and Agreement. Sociological Methods & Research, 42(3), 294–320. https://doi.org/10.1177/0049124113500475
Guetzkow, H. (1950). Unitizing and categorizing problems in coding qualitative data. Journal of Clinical Psychology, 6(1), 47–58. https://doi.org/10.1002/1097-4679(195001)6:1<47::AID-JCLP2270060111>3.0.CO;2-I
