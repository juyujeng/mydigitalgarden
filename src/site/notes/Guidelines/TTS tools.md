---
{"dg-publish":true,"permalink":"/Guidelines/TTS tools/","title":"文字轉語音工具","tags":["TTS","ai","guideline"],"created":"2025-05-22T22:05","updated":"2025-05-27T22:24"}
---

比較並試用幾個常見的文字轉語音（text-to-speech，TTS）的線上服務或單機開源工具。

目前有數量相當多的線上服務，都相當容易上手。但可以產生聽起來順耳的中文語音服務數量有限，隱私以及費用是主要的問題。

單機開源工具沒有隱私以及費用的問題，但技術門檻高，而且相當吃電腦硬體資源，一般的電腦要生成語音的速度大概都不會太快。可以產生聽起來順耳的單機開源工具也相當有限。

| 特性  | 線上服務 (Online Services)                             | 單機開源工具 (Offline Open-source Tools)      |
| --- | -------------------------------------------------- | --------------------------------------- |
| 優點  | 1. 易於使用： 無需安裝，透過網頁介面使用即可。                          | 1. 完全免費： 軟體本身及使用上沒有費用（訓練成本除外）。          |
|     | 2. 高品質語音： 雲端供應商通常提供高自然度、多樣化的語音。                    | 2. 數據隱私： 語音合成過程在本地進行，無需將數據上傳到雲端。        |
|     | 3. 無需本機硬體資源： 所有運算都在雲端進行，不佔用本機電腦資源。運算速度通常也比本機電腦快許多。 | 3. 客製化程度高： 程式碼開源，可以根據需求修改和優化。           |
|     | 4. 維護與更新： 服務商會定期更新和維護，無需自行管理。                      | 4. 不需網路： 一旦安裝，即可離線使用。                   |
|     | 5. 擴展性： 隨用隨付，可根據需求擴展使用量。                           |                                         |
| 缺點  | 1. 收費： 通常按使用量（字數）計費，長期或大量使用成本較高。                   | 1. 技術門檻高： 通常需要編寫程式碼、機器學習和語音處理等知識才能自在使用。 |
|     | 2. 數據隱私： 需要將文字內容上傳到雲端進行處理。                         | 2. 需要本機硬體資源： 尤其是訓練模型時需要強大的CPU/GPU。      |
|     | 3. 需要連上網路： 需要穩定的網路連線才能使用。                          | 3. 語音品質不一： 開源模型品質差異大，通常不如商業服務。          |
|     | 4. 客製化限制： 只能在服務商提供的選項內進行選擇，客製化彈性較低。                | 4. 維護與更新： 需要自行管理和更新，可能缺乏即時支援。           |
|     |                                                    | 5. 部署複雜： 安裝和設定過程可能較為繁瑣。                 |

## 線上TTS測試

我測試了五個服務讓它們唸一段中文文字。這些服務包含了雅婷、Ondoku、luvvoice、Elevenlab、TTSmaker。目前聽起來還是雅婷的中文聽起來最順耳，其次是Ondoku以及luvvoice。

[音檔]([https://drive.google.com/drive/folders/1Gijte8TXEcCqLPYO0_n4yPCNOXN0U1BQ?usp=sharing](https://drive.google.com/drive/folders/1Gijte8TXEcCqLPYO0_n4yPCNOXN0U1BQ?usp=sharing "https://drive.google.com/drive/folders/1gijte8txeccqlpyo0_n4ypcnoxn0u1bq?usp=sharing"))在此。

| 服務名稱      | 收費方式           | 是否可模仿聲音    | 備註                              |
| --------- | -------------- | ---------- | ------------------------------- |
| 雅婷        | 字數計費（298/10萬字） | 是（需透過 API） | 需使用 API 上傳音檔訓練模型，每帳戶最多保留五個聲音模型。 |
| Ondoku    | 按月計費           | 否          | 每月有字數上限                         |
| luvvoice  | 按月計費           | 是          | 每月有字數上限                         |
| Elevenlab | 按月計費           | 是          | 每月有字數上限                         |
| TTSmaker  | 按月計費           | 否          | 每月有字數上限                         |


## 單機TTS測試

研究如何部署中……（真的不簡單）。預計將先測試聯發創新基地釋出的[BreezeVoice](https://www.mediatek.tw/blog/%E8%81%AF%E7%99%BC%E5%89%B5%E6%96%B0%E5%9F%BA%E5%9C%B0%E5%85%A8%E9%9D%A2%E9%96%8B%E6%BA%90-breeze2)。