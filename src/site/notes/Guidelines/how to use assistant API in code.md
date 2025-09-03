---
{"dg-publish":true,"permalink":"/Guidelines/how to use assistant API in code/","title":"如何使用assistant API (in code)","tags":["chatgpt","ai","coding","LLMAI"],"created":"2024-09-08T16:28","updated":"2024-09-08T23:48"}
---

# 說明

本文分享使用 Assistants API 的操作流程、遭遇到的困難以及使用心得。 Assistants API 有兩種使用方法，這次分享in code的使用方法以及心得。

1. in playground：在OpenAI 的網頁上設定，並在網頁上與 ChatGPT 對話。我在[[Guidelines/how to use assistant API in playground\|上一篇]]分享了使用的方法以及心得。
2. in code：藉由程式（通常是python）與ChatGPT對話。


# 使用Python 與 Assistants API 溝通的步驟

以設定PEDro scale AI rater為例，約略分為5個步驟：

1. 到OpenAI 刷卡儲值credit
2. 安裝 `openai` module
3. 設定assistant
4. 開始對話
5. 儲存對話結果

## 1. 刷卡儲值credit

> [!Info] 說明
> 若要使用API需要先儲值一定的金額，再按照使用的token數扣款，不同的模型可能有不同的價格（詳見[OpenAI網頁](https://openai.com/api/pricing/)）。若不先儲值也可以先設定assistant，但沒辦法進行對話。為了接下來操作流暢，我將儲值放在第一步。

1. 開啟 OpenAI playground網頁，進到Billing頁面，按照頁面上的步驟輸入信用卡號儲值。
2. 可以選擇是否開啟 auto recharge ，當儲值金額不足時自動加值。
3. 可以到Limits頁面設定每個月的使用上限。

加值完之後便可以進到下一步，開始建立assistant！

## 2. 安裝 `openai` module並設定python環境參數

為python安裝 `openai` module。打開terminal，輸入

```
pip install openai
```

將APIKEY的文字儲存到工作資料夾中的`.env`檔案中的第一行，輸入

```plaintext
OPENAI_API_KEY = {貼上APIKEY的內容於此}
```


> [!NOTE] 為什麼要將APIKEY存在.env檔案中？
> 為了不讓APIKEY不小心在分享python code的過程中外洩，將APIKEY存在另一個獨立的檔案中。


```python
# import會用到的module

import openai # openai是必要的
from dotenv import find_dotenv, load_dotenv # 為了讀取apikey
import os
import time
import logging
from datetime import datetime


# 設定環境變項，每一輪的評分都一樣不會變

load_dotenv()
APIKEY = os.getenv("OPENAI_API_KEY") # APIKEY寫在.env檔案當中
client = openai.OpenAI(api_key = APIKEY)
```

## 3. 設定assistant

利用以下code建立一位assistant

```python
assistant = client.beta.assistants.create(name="PEDro AI rater prompt4", instructions=instr_texts, tools=[{"type": "file_research"}], model="gpt-4o", "top_p": 1.0,   "temperature": 0.4, "response_format": "text")
```

完成之後，使用`print(assistant.id)`獲得重要的assistant id，未來每一次的對話都需要用這個id來指定要溝通的對象。不過，我認為用playground設定一位新的assistant可能比較方便。（見[[Guidelines/how to use assistant API in playground#2. 設定assistant\|how to use assistant API in playground#2. 設定assistant]]）設定完之後，同樣可以在playground當中獲得assistant id：
 ![截圖 2024-09-08 23.13.38.jpg](/img/user/Guidelines/%E6%88%AA%E5%9C%96%202024-09-08%2023.13.38.jpg)

## 4. 開始對話

在要進行對話的時候，需要分別建立`thread`、`message`。前者可以將它視為使用chatgpt時的對話視窗，而後者則是每一次的互動對話。建立完`message`後，還需要執行`run`，才會開始運算。

```python
# 建立thread（對話串）
thread = client.beta.threads.create()

# 將檔案上傳至OPENAI
message_file = client.files.create(
file=filepath, # 要上傳的檔案路徑
purpose="assistants" # 請根據需要調整用途，例如 'answers', 'search', 'fine-tune' 等
)
# 取得上傳檔案的file id（每一個上傳的檔案都會有一個id）
file_id = message_file.id 

# 在thread中新增對話  
message = client.beta.threads.messages.create(thread_id=thread.id,
role="user",content=prompt_txt, 
# 在對話當中新增附件
attachments=[{ "file_id": file_id, "tools": [{"type": "file_search"}] }]
)

  

# 執行對話（就像是在chatgpt當中輸入完prompt，按下run）  
run = client.beta.threads.runs.create(
thread_id=thread.id,
assistant_id=assistant_id
)
```

## 5. 儲存對話結果

執行`run`之後並不會獲得回應，還需要進一步頡取回應的結果。但是回應需要生成時間，並不是執行完就可以馬上獲得回應。我們可以寫一個函式，定時檢查是否完成回應，再將回應輸出。

```python
# 設定輸出的函式
def wait_for_run_completion(client, thread_id, run_id, file_no, output_folder, sleep_interval=5):
    """

    Waits for a run to complete and prints the elapsed time.:param client: The OpenAI client object.
    :param thread_id: The ID of the thread.
    :param run_id: The ID of the run.
    :param sleep_interval: Time in seconds to wait between checks.
    """

    start_time = time.time() # 計時開始
    timeout = 5 * 60 # 超過5分鐘就跳下一個
    while True:
        if time.time() - start_time > timeout:
            print(f"Processing for file {file_no} exceeded 5 minutes. Skipping this file.")

            # 超過時間，先將thread.id和run.id儲存下來，日後再試
            output_folder = "api evaluation results"
            os.makedirs(output_folder, exist_ok=True)
            fail_filename = f"{file_no}_fail.txt"  # 使用 file number 生成失败的文件名
            fail_output_path = os.path.join(output_folder, fail_filename)

            with open(fail_output_path, "w", encoding="utf-8") as f:
                f.write(f"File no: {file_no}\n")
                f.write(f"Thread ID: {thread_id}\n")
                f.write(f"Run ID: {run_id}\n")

            print(f"Failure details saved to {fail_output_path}")
            return  # 跳過這一輪
        try:
            run = client.beta.threads.runs.retrieve(thread_id=thread_id, run_id=run_id)
            if run.completed_at:
                elapsed_time = run.completed_at - run.created_at
                formatted_elapsed_time = time.strftime(
                    "%H:%M:%S", time.gmtime(elapsed_time)
                )
                print(f"Run completed in {formatted_elapsed_time}")
                logging.info(f"Run completed in {formatted_elapsed_time}")
                # Get messages here once Run is completed!
                messages = client.beta.threads.messages.list(thread_id=thread_id) # 會獲得這個thread裡所有的messages
                last_message = messages.data[0]
                response = last_message.content[0].text.value
                print(f"Assistant Response: {response}")

                # 將完成時間和response輸出到"api evaluation results"資料夾中
                output_folder = output_folder
                os.makedirs(output_folder, exist_ok=True)
                filename = f"{file_no}.txt"  # 使用 file number 作為檔名
                output_path = os.path.join(output_folder, filename)
                
                with open(output_path, "w", encoding="utf-8") as f:
                    # 第一行寫入完成時間
                    f.write(f"Run completed in {formatted_elapsed_time}\n")
                    # 第二行開始寫入response的內容
                    f.write(response)

                print(f"Response saved to {output_path}")
                break
        except Exception as e:
            logging.error(f"An error occurred while retrieving the run: {e}")
            break
        logging.info("Waiting for run to complete...")
        time.sleep(sleep_interval)

```


> [!ATTENTION] 生成回應可能會失敗
> 生成回應可能會失敗，過了很久仍然沒有完成。可能是語言模型發生錯誤。我這邊設定如果嘗試過了5分鐘，就跳過。並儲存一個文字檔，標示發生錯誤的評分目標pdf檔為何。
> 就算沒有成功獲得回應，同樣是要扣儲值的…
