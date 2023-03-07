---
{"dg-publish":true,"permalink":"/Blog/Research/openAI API的初步瞭解/","title":"openAI API的初步瞭解","tags":["blog","ai","chatgpt"]}
---


# openAI API的初步瞭解

## 什麼是API

API的全名是Application Programming Interface，它是用來讓使用者可以透過其他的程式軟體來和openAI溝通，讓使用者可以在自己撰寫的程式軟體當中跟openAI收、發訊息。

根據openAI API的[手冊](https://platform.openai.com/docs/api-reference/introduction)，可以使用python、Node.js，或是其他可以透過HTTP向openAI傳送訊息的程式來連接到openAI。

## 使用API的優點

### 可以更快速地與AI溝通

透過API連接的方式，使用者可以在利用自己所撰寫的程式，更方便快速地與openAI對話。例如，有一百份會議紀錄需要請openAI進行重點整理，若不用API便要自己一份一份地貼到chatGPT對話視窗，但若使用API，便可以用電腦程式自動傳送訊息給AI，然後截取回送的摘要存成想要的格式。


### 可以訓練自己的模型

根據[手冊](https://platform.openai.com/docs/guides/fine-tuning)介紹，使用者可以透過API上傳training data給openAI，以此訓練出個別化的模型。如果用來訓練的資料越結構化，品質越好，訓練出來的模型品質也越好。

如果想要訓練出獨特的語言使用習慣，或是獨特的語言使用偏好的AI，就得要透過API這個方式上傳足夠的訓練資料。

未來如果想要發展標準病人AI，勢必要透過這個方式來進行。

## 使用API的限制

1. 需要足夠程度的程式撰寫能力
2. API的使用每個月有訊息傳送的免費額度，超過要加錢，隨著使用的模型不同而有不同的[收費標準](https://openai.com/pricing#InstructGPT)
3. 若要訓練自己的模型也要加錢