---
{"dg-publish":true,"permalink":"/雅婷API測試/","title":"雅婷API測試","tags":["python","api","TTS","ai"],"created":"2025-05-26T22:00","updated":"2025-05-26T23:01"}
---

## 文字轉語音（text-to-speech，TTS）

文字轉語音可以使用雅婷團隊寫好的 [python 套件](https://github.com/TaiwanAILabs-Yating/tts-sdk-python)來進行文字轉語音。

### 1. 安裝`Yating-TTS-SDK`

```cmd
pip install Yating-TTS-SDK
```

### 2. 使用方式

1. 呼叫`Yating-TTS-SDK`
2. 提供相關的文字以及資訊
3. 完成後儲存為音檔

```python
from yating_tts_sdk import YatingClient as ttsClient

URL = "https://tts.api.yating.tw/v2/speeches/short"
KEY = "將API key貼上"


TEXT = "大成宮！慧成宮！龍成宮！用API真的好難啊！" 
# 要AI唸的文字

TEXT_TYPE = ttsClient.TYPE_TEXT
MODEL = "zh_en_female_1"

# model 目前有雅婷、意晴、家豪、志明（見下表）

SPEED = 1.0
PITCH = 1.0
ENERGY = 1.0
ENCODING = ttsClient.ENCODING_MP3
SAMPLE_RATE = ttsClient.SAMPLE_RATE_16K
FILE_NAME = "yating test"

try:
    client = ttsClient(URL, KEY)
    client.synthesize(TEXT, TEXT_TYPE, MODEL, SPEED, PITCH, ENERGY, ENCODING, SAMPLE_RATE, FILE_NAME)
except Exception as err :
    print("An exception occurred:", err)
```

※ 完成後的[音檔](https://drive.google.com/file/d/1wZvYtT_v07FVl4JZaULBk0lpfaruGLLn/view?usp=sharing)

### 聲音模型

| Variables      | Type             | Info                                  |
| -------------- | ---------------- | ------------------------------------- |
| zh_en_female_1 | Female1 (Yating) | 雅婷AI人聲                                |
|                |                  | Mandarin and English, support 22K/16K |
| zh_en_male_1   | Male1 (Jiahao)   | 家豪AI人聲                                |
|                |                  | Mandarin and English, support 22K/16K |
| zh_en_female_2 | Female2 (Yiqing) | 意晴AI人聲                                |
|                |                  | Mandarin and English, support 22K/16K |
| zh_en_male_2   | Male2 (Zhiming)  | 志明AI人聲                                |
|                |                  | Mandarin and English, support 22K     |
| tai_female_1   | Female1 (Yating) | 雅婷AI人聲                                |
|                |                  | Taiwanese, support 16K                |
| tai_male_1     | Male1 (Jiahao)   | 家豪AI人聲                                |
|                |                  | Taiwanese, support 16K                |
| tai_female_2   | Female2 (Yiqing) | 意晴AI人聲                                |
|                |                  | Taiwanese, support 16K                |



## 聲音複製（未完成）

上傳聲音之後，一直無法完成模型訓練。

### 程式碼

```python
import requests
import json
import time

class YatingVoiceCloneClient:
    BASE_URL = "https://tts.api.yating.tw"

    def __init__(self, api_key):
        self.api_key = api_key
        self.headers = {
            "key": self.api_key,
            "Content-Type": "application/json"
        }

    def create_model(self, speaker_id, audio_uri):
        url = f"{self.BASE_URL}/v3/voice-cloning/models"
        data = {
            "speakers": [
                {"speakerId": speaker_id, "audioUri": audio_uri}
            ]
        }
        response = requests.post(url, headers=self.headers, json=data)
        return response.json()

    def get_model_status(self, uid=None):
        if uid:
            url = f"{self.BASE_URL}/v3/voice-cloning/models/{uid}"
        else:
            url = f"{self.BASE_URL}/v3/voice-cloning/models/"
        response = requests.get(url, headers=self.headers)
        return response.json()

    def delete_model(self, uid):
        url = f"{self.BASE_URL}/v3/voice-cloning/models/{uid}"
        response = requests.delete(url, headers=self.headers)
        return response.status_code == 200

    def synthesize(self, text, model_id, speaker_id, lang="zh_tw", encoding="LINEAR16"):
        url = f"{self.BASE_URL}/v3/voice-cloning/speeches"
        data = {
            "input": {"text": text, "type": "text"},
            "voice": {"modelId": model_id, "speakerId": speaker_id, "lang": lang},
            "audioConfig": {"encoding": encoding, "maxLength": 600000}
        }
        response = requests.post(url, headers=self.headers, json=data)
        return response.json()

    def get_synthesis_status(self, uid=None):
        if uid:
            url = f"{self.BASE_URL}/v3/voice-cloning/speeches/{uid}"
        else:
            url = f"{self.BASE_URL}/v3/voice-cloning/speeches"
        response = requests.get(url, headers=self.headers)
        return response.json()

    def download_audio(self, audio_url, file_path):
        response = requests.get(audio_url)
        if response.ok:
            with open(file_path, "wb") as file:
                file.write(response.content)
            return True
        return False


client = voiceclone.YatingVoiceCloneClient(api_key="APIKEY")
# 建立模型
create_result = client.create_model("my_speaker1j", "paste url here")
print(create_result)

# 查詢模型建立狀態（需要等一段時間）
status = client.get_model_status(create_result['uid'])
print(status)
# 目前一直顯示ongoing，已經數小時了，不正常
```

## 後記

雅婷在創立API帳號之後會送1000點，本想說會相當充裕，但想不到試了文字轉語音，以及多國語言配音兩個功能之後就沒錢了。才發現只要呼叫該功能一次，便會從1000點裡面扣該功能的計費單位。
我在測試的過程中分別使用了兩個功能短短的產生了幾個字，但就已經先扣了`298+596=894`。我本來以及我要用到十萬字才會扣該單位的金額。

| 分類    | 功能         | 價格            |
|-------|------------|---------------|
| 語音轉文字 | 語音轉文字-即時   | TWD 96 每小時音訊  |
|       | 語音轉文字-音檔辨識 | TWD 144 每小時音訊 |
| 文字轉語音 | 文字轉語音      | TWD 298 每十萬字元 |
|       | 多國語言配音     | TWD 596 每十萬字元 |
| 事件分群  | 全球即時事件     | TWD 20 每次查詢   |
| 虛擬主播  | 虛擬主播影片生成   | TWD 20 每15秒影訊 |
