---
{"dg-publish":true,"permalink":"/Guidelines/how to use assistant API in playground/","title":"如何使用assistant API (in playground)","tags":["chatgpt","ai","LLMAI","coding"],"created":"2024-08-14T22:26","updated":"2024-08-14T22:27"}
---


# 說明

本文分享使用 Assistants API 的操作流程、遭遇到的困難以及使用心得。 Assistants API 有兩種使用方法，本文先分享第一種：
 1. in playground：在OpenAI 的網頁上設定，並在網頁上與 ChatGPT 對話
 2. in code：藉由程式（通常是python）與ChatGPT對話。

Assistants API 是 OpenAI 公司提供的服務，目前處於beta階段，讓使用者可以透過 API 在自己設計的程式或是服務當中與 ChatGPT 溝通。

與 MyGPTs 相同的功能包含：
1. 藉由 instruction 製定 ChatGPT 使用的情境與要求
2. 籍由 File search 工具上傳文件給 ChatGPT
3. 籍由code interpreter讓  ChatGPT 可以執行 python 程式，並處理多種格式的檔案
4. 籍由function calling讓  ChatGPT 可以與外部的程式互動

==與MyGPTs不同之處在於，使用 Assistants API 可以自定兩個參數（[[GPTs可以調整的參數\|temperature、top P]]），調整語言模型回應內容的隨機性。==

# 在playground使用 Assistants API 的步驟

以設定PEDro scale AI rater為例，約略分為4個步驟：
1. 到OpenAI 刷卡儲值credit
2. 設定assistant
3. 開始對話
4. 儲存對話結果

## 1. 刷卡儲值credit


> [!Info] 說明
> 若要使用API需要先儲值一定的金額，再按照使用的token數計費，不同的模型可能有不同的價格（詳見[OpenAI網頁](https://openai.com/api/pricing/)）。若不先儲值也可以先設定assistant，但沒辦法進行對話。為了接下來操作流暢，我將儲值放在第一步。 

1. 開啟 OpenAI playground網頁，進到Billing頁面，按照頁面上的步驟輸入信用卡號儲值。
2. 可以選擇是否開啟 auto recharge ，當儲值金額不足時自動加值。
3. 可以到Limits頁面設定每個月的使用上限。

加值完之後便可以進到下一步，開始建立assistant！

## 2. 設定assistant

1. 進到[playground頁面](https://platform.openai.com/playground/chat)
2. 於畫面左邊的面版選擇assistant
   ![Pasted image 20240814231650.png](/img/user/Guidelines/Pasted%20image%2020240814231650.png)
3. 點選「create」新增Assistant
4. 按照畫面上的欄位輸入必要的資訊
    1. Name: 這個AI assistant的名稱，例如`PEDro scale AI rater (prompt4)`
    2. Instructions: 要 assistant 執行的任務說明或指令。我在此輸入single item prompt所有內容
    3. Model: 選擇要使用的語言模型版本，如gpt-4o（若沒有先儲值，只有4o-mini以及3.5可以選擇）
    4. Tools: 可以都不開（隨時可以更改）
        1. File search: 上傳文件存進GPT的資料庫（專有名詞為vector store）。PEDro AI rater應該只需要這個。
        2. code interpreter: 讓GPT可以執行python。==這個功能每使用一次要0.03鎂！==
    5. Response format: 使用text
    6. Temperature: 0 ~ 2之間的數值，預設是1，嘗試設為0.4。
    7. Top P: 根據說明文件，更改temperature時這個保持不動。


> [!Question] Instructions vs. prompt
> PEDro scale的各題評分標準應該放在instructions裡，還是每次評分時作為prompt輸入呢？
> 根據[OpenAI 討論區](https://community.openai.com/t/what-are-the-differences-between-instructions-and-the-instructed-prompts/831441)，Instructions 給予AI一個任務的方向與作業準則，而prompt 則提供較特定的要求。因此，應該將PEDro scale各題評分標準放在instructions較合乎上述的原則。然而，在PEDro scale AI rater的例子中，使用的目的與方法相當地固定，所以無論放在哪一邊都可以。
> 不過，若放在prompt，每次對話要處理的token數會比較多，比較快會把儲值花完。所以應該放在instructions會比較好。


> [!Tip] File search
> 上傳的文件會存到某一個vector store當中，可以在對話時指定要使用的vector store。在PEDro scale AI rater的例子當中，為了怕不同的文章彼此干擾，需要建立上百個不同的vector store。這些被建立的vector store都會被儲存下來，可以在OpenAI dashboard的Storage當中看到。

## 3. 開始對話

1. 上傳要評分的pdf檔：點選迴蚊針符號→File search→click to upload→選擇pdf→點選Attach
   ![Pasted image 20240814235635.png](/img/user/Guidelines/Pasted%20image%2020240814235635.png)
2. 輸入prompt：`1. print the title of article I upload. 2. evaluate this article with PEDro scale`
3. 按下 **Run**
    1. 可以在畫面右邊的log檢視是否完成對話（顯示 Run completed）。中間的對話視窗有時候會過好一陣子才完成輸出，==還會重複地列印之後又刪除==。

![Pasted image 20240815001010.png](/img/user/Guidelines/Pasted%20image%2020240815001010.png)


## 4. 儲存對話結果


> [!Important] 重要！
> 在playground中和assistant的對話（在這裡的專業名詞為thread）不會被保留下來。需要另外複製貼上為其他文字檔！

## 開啟新的對話進行評分

可以看到，在原來的對話右上角顯示目前對話的vector store包含一個文件。若想要進行新的評分而不受到舊文件的影響，需要更新文件。
   ![Pasted image 20240815001131.png](/img/user/Guidelines/Pasted%20image%2020240815001131.png)
### 方法一：更新vector store

1. 更新vector store當中的檔案：點選對話右上角vector store圖示，再點選file search，上傳新的檔案
   ![截圖 2024-08-15 00.12.43.jpg](/img/user/Guidelines/%E6%88%AA%E5%9C%96%202024-08-15%2000.12.43.jpg)
2. 上傳完新文件之後，再一次點選對話右上角vector store圖示，再點選Untitled storage處。將舊的文件刪除之後關閉。
   ![Pasted image 20240815001824.png](/img/user/Guidelines/Pasted%20image%2020240815001824.png)
3. 再一次輸入prompt：`1. print the title of article I upload. 2. evaluate this article with PEDro scale`，按下Run

### 方法二：Clear the thread

![Pasted image 20240815002446.png](/img/user/Guidelines/Pasted%20image%2020240815002446.png)

1. 點選對話右上角的掃把圖示，它會將對話的內容以及vector store全部清除。
2. 重複上面[[Guidelines/how to use assistant API in playground#3. 開始對話\|3. 開始對話]]的步驟