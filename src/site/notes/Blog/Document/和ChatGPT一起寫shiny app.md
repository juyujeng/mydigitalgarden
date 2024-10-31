---
{"dg-publish":true,"permalink":"/Blog/Document/和ChatGPT一起寫shiny app/","title":"和ChatGPT一起寫shiny app","tags":["chatgpt","note","blog","R","shiny","research"],"created":"2024-10-31T13:28","updated":"2024-10-31T16:35"}
---


OpenAI的ChatGPT近期又推出了新功能[Canvas](https://openai.com/index/introducing-canvas/)，它讓使用者可以更容易和ChatGPT合作完成一篇文章或是程式碼。趁著這個機會，我想到和ChatGPT一起合作利用`R`語言撰寫一個`shiny app`，用來自評[[self evaluated 8 core abilities\|研究八大核心能力]]。
在ChatGPT的協助下，我的確很快的在不到半小時就將初版的[自評網站](https://drgttsu.shinyapps.io/myshinyapp/)上線了。

但隨著想要達到的功能和排板增加，我馬上就遭遇到相當嚴重的問題。隨著想要達到的功能越來越多，程式碼越來越長，ChatGPT常常沒有辦法完成程式碼的修改。程式碼寫到一半ChatGPT就認為自己已經完成便停了下來。需要一再地要求它繼續完成。也許是因為在我要求新增功能或是排版之後，ChatGPT總是從頭開始重新編輯一次程式碼，所以在處理到一半時便達到了處理token的上限。

除了這個相當明顯的缺點外，Canvas功能可以相當快速地幫我完成初步的程式架構，是很棒的一項功能！