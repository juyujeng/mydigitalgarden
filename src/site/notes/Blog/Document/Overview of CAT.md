---
{"dg-publish":true,"permalink":"/Blog/Document/Overview of CAT/","title":"電腦適性測驗概述","tags":["blog","CAT","adaptive_testing"],"created":"2023-08-17","updated":"2023-08-17"}
---


## 背景

電腦適性測驗（computerized adaptive test，CAT）為了提供比傳統測驗更準確以及更有效率的測量

- 更準確的測量：
    - 藉由增加測量題目可以獲得的訊息量（information）減少對受測者能力估計的誤差（見[[Test information function\|Test information function]]）
    - 理想狀態下，每一題的選擇都是當前步驟能夠提供最多訊息的題目

## 題庫發展

- 決定測驗的目的
    - 能力測驗（Proficiency Test）：用來評估個人在特定領域或主題的能力或知識。這類測驗通常不關注受測者是否通過了特定課程或訓練，而是衡量他們在某一領域的總體能力和熟練程度。如：語言能力測驗。
    - 分類測驗（Classification Test）：用於將受測者依照特定標準分組或分類。這種測驗通常用於確定個人是否具備特定的資格或滿足特定的標準，並根據結果將他們分入不同的類別。如廚師資格考試。
- 發展足夠的題目數
    - 應包含各種難度的題目
- 檢驗題目的品質（內容效度、表面效度）
- 施測題目
- items calibration（題目驗證、驗證題目參數，未找到統一的翻譯）

## 執行步驟



<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">




==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
選擇初始題目
或題組開始測驗 ^XgbKWAjn

中途估計
受測者能力 ^nexiAgp9

更新受測者的反應模式 ^3ZPr4MsA

選擇下一題
施測題目 ^Iea3YzwP

最終受測者
能力估計 ^HNTwAmXH

滿足終止條件？ ^iRaLLbi0

結束測驗 ^eUEf7RdE

否 ^3LbOfWmB

是 ^Giqp34Fd

Starting step ^NCTNJjJ3

Test step ^RkfqbV2O

Stopping step ^qpyf4Qi1

Final step ^bmiKkEKU



</div></div>



### initial step

- 自題庫當中選擇至少1題開始進行測驗
- 若沒有受測者能力相關的先驗知識，通常是以受測群體的平均能力所對應的題目
- 但要避免對所有的受測者都使用同一題起始，容易讓題目洩露

### test step

1. 以目前受測者的答題情況估計受測者的能力
2. 如果終止條件未滿足，
    - 下一題按照選題方式，自題庫中選擇符合條件的題目
    - 更新受測者的答題情況
    - 回到步驟1
3. 如果終止條件滿足，終止施測，計算受測者能力

#### 能力估計方式

- maximum likelihood
- weighted likelihood
- Bayesian estimators
- 使用時不一定要從頭到尾都使用同一種估計方式，可以採用混合模式。例如：一開始用一種估計方式，在施測一定數量的題目之後改用另一個

#### 選題方式

列舉幾種文獻上常見的選題方式，各方式有其優缺點。目前最常見的是The maximum Fisher information (MFI) criterion。

1. The maximum Fisher information (MFI) criterion
2. The so-called bOpt criterion, also sometimes referred to as Urry’s rule
3. The maximum likelihood weighted information (MLWI) criterion
4. The maximum posterior weighted information (MPWI) criterion
5. The Kullback-Leibler (KL) divergency criterion
6. The posterior Kullback-Leibler (KLP) criterion
7. The maximum expected information (MEI) criterion
8. The minimum expected posterior variance (MEPV) criterion
9. The so-called thOpt procedure
10. The progressive method
11. The random selection among available items: the benchmark selection method for simulation studies

### stopping step

有四種終止條件。一般來說一個測驗只會設定一種終止條件。但也可以設定複合式的終止條件，只要條件之一滿足即終止測驗

- The length criterion：設定施測題目數量的上限，當施測的題目數到達上限時即終止測驗 
- The precision criterion：當對受測者的能力估計的誤差低於某個設定的標準時即終止施測（或是信度高於某個標準時）
- The classification criterion：用在測量受測者的能力是否達到某個程度的測驗。實際使用時會先設定某個能力標準，當受測者的能力估計值之信賴區間與設定的能力標準不重疊時終止施測（也就是能力顯著地高於或是低於標準）
- The information criterion： focuses on the amount of information that is carried by each item at the provisional ability estimate. A necessary condition for the CAT to continue is that the remaining eligible items share enough information to make the total information increase significantly. For this rule, the threshold is the minimum information carried by at least one of the eligible items. If, at the provisional ability estimate, all eligible items have information values smaller than the predefined threshold, the CAT stops. This criterion can be used to avoid administering items that do not carry enough information to the ability estimation and related precision. （關於information還未參透，參透後再回來修改）

### final step

- 計算最終對受測者能力的估計值
- 可以用與test step中一樣的估計方式，也可以在這一階段合併使用其他的估計方式