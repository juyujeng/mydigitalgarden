---
{"dg-publish":true,"permalink":"/determining sample size/","title":"如何決定樣本數？","tags":["guideline","statistics"],"created":"2024-02-05T16:18","updated":"2024-02-21T15:15"}
---


## 為什麼要估計樣本數？

估計需要的樣本數是在研究準備過程中很重要的一步，如果在資料開始蒐集之後才想到就來不及了。

- 行政上，樣本估計可以協助達到較佳的資源分配（時間以及金錢）。
- 分析上，樣本估計可以事先評估
  - 對目標母群參數估計的準確程度（描述統計）是否合乎需求
  - 對特定效果量的統計檢定力（推論統計）是否合乎預期

## 樣本數估計流程

Bujang（2021）認為研究的樣本估計流程應包含5個步驟：

1. 瞭解研究的主要目的（目標參數）
2. 選擇適當的統計分析方法
3. 根據分析方法計算最少需要的樣本
4. 考量可能的無效樣本比率，決定實際上要蒐集的樣本數
5. 將前述步驟的執行方法與思路紀錄下來

其中，步驟1到4是在研究中一般樣本估計常見的流程，但是目前文獻上不同研究對於樣本數如何估計的描寫方式不盡相同。Bujang（2021）想要提供一個可以讓研究者在撰寫相關段落時有可以依循的步驟，因此多提了第5步。

## 描述統計的樣本數估計

描述統計目標是要估計母群的參數，而這需要有足夠的樣本數才可以得到可信的樣本估計。在計算需要的樣本數時，針對不同的參數（如：平均、發生率）有不同的適用公式（Sapra, 2022）。不同的公式主要的差異在於對於參數的誤差分佈的假設（高斯、或是其他分配）。在計算時有幾個需要考量的參數：

- 研究想要達到的信心程度
  - 90%？95%？99%？由研究者決定。
  - 根據不同的信心程度，再搭配參數的誤差分佈的假設，在計算時需要轉換為相對應的數值（例如若要達到95%信心程度，且假設參數的誤差分佈為標準化常態分佈，則要將95%信心程度轉為$Z$值，也就是1.96）。
- 對估計值的測量精準度或是測量誤差
  - 測量精準度是測量誤差的倒數，是參數估計的可信程度。測量誤差包含了隨機誤差以及系統誤差。
  - 這個值可以是已知工具的測量誤差值（如[[standard error of measurement\|SEM]]），或是研究者可以容許的測量誤差值。
    - 訂定容許的測量誤差值時可以定**絕對誤差值**（例如 2 個測量單位）或是**相對誤差值**（例如參數估計值的3%），視研究的需求而定。
- 預期的平均數、標準差
  - 也就是預期測量樣本會得到的平均數以及標準差。可以從既有的研究報告或是 pilot study 數據獲得。

### 估計平均數所需的樣本數

#### 計估公式

根據 Sapra（2022, p 85），若想要計算可以達到對母群平均數有可信估計，可以使用以下公式

$n \ge \frac{Z^2\sigma^2}{d^2}$
其中，

- $n$為最少需要的樣本數
- $Z$為對應信心程度的$Z$值，例如95%信心程度的$Z$值為1.96。這是因為假設平均數的測量誤差分佈為標準化常態分佈，才會套用$Z$分佈。
- $\sigma$為預期可能得到的標準差
- $d$為測量誤差，或是可容許的誤差大小（要和$\sigma$相同的單位，若是使用相對誤差時要特別注意記得換算）

#### 例1

> [!EXAMPLE] 假設我們想要以問卷估計生成式AI初學者對於「能正確地判斷AI給予的回應是否正確」的自我效能平均分數。而pilot study 的結果其平均為6.1分，標準差為 1.8。在95%的信心水準下，想要對母群平均得到容許的測量誤差為±1分的估計，最少應該蒐集多少樣本數？
>
> - 代入上述的公式 $n \ge 1.96^2*1.8^2/1^2 = 12.45$
> - 因此，最少需要蒐集13人的樣本

#### 例2：重複測量

> [!EXAMPLE] 若假設我們想要以某測量工具 T 測量個體 X 能力分數。若想多次測量個體之後取平均作為該個體 X 能力的分數。在95%信心水準下，若想讓對個體能力估計誤差±0.3分內，應至少重複測量多少次？ （假設沒有練習效果，不同次測量間只存在隨機誤差，工具 T 的SEM = 1.5）

這也是一個常見的例子。但前面的平均數樣本估計主要討論的是組平均（不同個體之間的平均），而這個例子卻是同一個個體多次重複測量之後取平均。雖然文獻當中大多不是在討論這種重複測量的情況，但如果假設重複測量之間沒有練習效果，每次的測量間只存在獨立的隨機誤差，那應該也可以用同樣的原則來計算重複測量的數量。只是在重複測量的情況下，研究者所**能接受的誤差大小應該更小**。

> [!Note] 若假設我們想要以某測量工具 T 測量個體 X 能力分數。已知若想多次測量個體之後取平均作為該個體 X 能力的分數。在95%信心水準下，若想讓對個體能力估計誤差±0.3分內，應至少重複測量多少次？ （假設沒有練習效果，不同次測量間只存在隨機誤差，工具 T 的SEM = 1.5）
>
> - 代入上述的公式 $d = 0.3$、$\sigma = SEM$
>   - ※ 這裡使用SEM代入$\sigma$ 這是因為假設每次測量只有隨機誤差，故重複測量到的結果標準差應該等於SEM。否則應該要做pilot study，實際進行重複測量之後計算標準差。
> - $n \ge \frac{1.96^2 1.5^2}{0.3^2} = 96.04$
> - 因此，最少需要重複測量97次

## 推論統計的樣本數估計

- 需要考量的參數
  - $\alpha$: type I error rate
  - $\beta$: type II error rate
  - effect size

... 細節待補

## 心得

過去在進行樣本數估計時，我所受的訓練都是集中在推論統計，主要考量的是實驗操弄的效果是否能夠被統計方法檢驗出來，對於母群參數估計的準確度或是可信度就沒那麼關心。因為不同組別都是用同樣的方法測量，誤差對所有組別應該都是一樣的。只要樣本數夠大，讓實驗操弄的效果可以顯現即可。這是第一次對於參數估計的準確度或是可信度所需要的樣本數估計有更進一步的認識，值得紀錄。

此外，描述統計中對於n的計算，似乎可以理解為測量誤差跟估計標準誤的比值需要大於信心水準。這個理解從公式來

$$n \ge Z^2\sigma^2/d^2$$
移項之後可以得到
$$\frac{d^2}{\sigma^2}n \ge Z^2$$
而這又可以改寫為
$$\frac{d^2}{\sigma^2/n} = \frac{d^2}{se^2}\ge Z^2$$
也就是
$$\frac{測量誤差}{估計標準誤} \ge Z$$

## 參考文獻

Bujang, M. A. (2021). A Step-by-Step Process on Sample Size Determination for Medical Research. *Malaysian Journal of Medical Sciences*, *28*(2), 15–27. <https://doi.org/10.21315/mjms2021.28.2.2>

De Vet, H., Terwee, C., Mokkink, L., & Knol, D. (2011). Reliability. In *Measurement in Medicine: A Practical Guide* (Practical Guides to Biostatistics and Epidemiology, pp. 96-149). Cambridge: Cambridge University Press. doi:10.1017/CBO9780511996214.006

Sapra, R. L. (2022). How to Calculate an Adequate Sample Size? In S. Nundy, A. Kakar, & Z. A. Bhutta, *How to Practice Academic Medicine and Publish from Developing Countries?* (pp. 81–93). Springer Nature Singapore. <https://doi.org/10.1007/978-981-16-5248-6_9>
