---
{"dg-publish":true,"permalink":"/Gewt's AC/","title":"Gewt's AC","tags":["agreement","reliability","guideline","statistics"],"created":"2025-03-10T23:05","updated":"2025-03-11T00:04"}
---


## Kappa paradox

Kappa paradox 指 Cohen's kappa 在某些情況下，可能發生兩位評分者的評分一致百分比（percentage of agreement）和 Cohen's kappa 結果差異很大的情況。例如一致百分比高，但是 Cohen's kappa低；或是一致百分比低而 Cohen's kappa 高。

## 發生Kappa paradox的情境

### 邊際總數不平衡

當列聯表 (contingency table) 的邊緣總數（即行總和或列總和）存在嚴重不平衡時，即使觀察到高 agreement，Kappa 值也可能大幅降低。這種情況在實際研究中經常發生，特別是在某個（或某些）分類結果觀察到的次數遠高於其他分類結果觀察到的次數時。
- 例如：如下表所示，兩個評分者評分為1的情況遠高於評分為0或2
	- Cohen's kappa = 0.000
	- percentage of agreement = 0.967

| Rater 2 \ Rater 1 | 0 | 1  | 2  | **總計** |
|--------------------|---|----|----|-----------|
| 0                  | 0 | 0  | 0  | 0         |
| 1                  | 0 | 29 | 0  | 29        |
| 2                  | 0 | 1  | 0  | 1         |
| **總計**           | 0 | 30 | 0  | 30        |



### 邊際分佈呈不對稱

指列聯表對角線以外的數值分佈不均勻。這可能跟評分者的評分能力有偏誤（bias），或是某個分類結果的盛行率（prevalence）很高（或很低）有關。
- 例如：如下表所示，資料集中在對角線的下半部
	- Cohen's kappa = 0.282
	- percentage of agreement = 0.533

| Rater 2 \ Rater 1 | 0  | 1  | 2  | **總計** |
|--------------------|----|----|----|-----------|
| 0                  | 10 | 1  | 0  | 11        |
| 1                  | 5  | 3  | 0  | 8         |
| 2                  | 7  | 1  | 3  | 11        |
| **總計**           | 22 | 5  | 3  | 30        |


## Gewt's AC 

Gewt 提出 AC 指標，它可以克服前述造成kappa paradox的邊際機率問題，或是偏誤、盛行率問題。

| Rater 2 \ Rater 1 | 0 | 1  | 2  | **總計** |
|--------------------|---|----|----|-----------|
| 0                  | 0 | 0  | 0  | 0         |
| 1                  | 0 | 29 | 0  | 29        |
| 2                  | 0 | 1  | 0  | 1         |
| **總計**           | 0 | 30 | 0  | 30        |

- Cohen's kappa = 0.000
- Gewt's AC = 0.966
- percentage of agreement = 0.967

| Rater 2 \ Rater 1 | 0  | 1  | 2  | **總計** |
|--------------------|----|----|----|-----------|
| 0                  | 10 | 1  | 0  | 11        |
| 1                  | 5  | 3  | 0  | 8         |
| 2                  | 7  | 1  | 3  | 11        |
| **總計**           | 22 | 5  | 3  | 30        |

- Cohen's kappa = 0.282
- Gewt's AC = 0.335
- percentage of agreement = 0.533

### Gwet's AC 的報告方式

AC 值的範圍為 0 到 1，其中 0 表示僅有隨機一致性，1 則代表完全一致。AC 的詮釋標準目前尚未有普遍被接受的指標。或可先參考Cohen's kappa的詮釋標準。另外，除了報告 AC 係數外，建議同時提供 95% 信賴區間（Confidence Interval, CI），以說明估計值的精確程度。這有助於讀者更清楚地了解結果的可靠性。

- 0.00–0.20: 一致性極差（Poor agreement）
- 0.21–0.40: 一致性尚可（Fair agreement）
- 0.41–0.60: 一致性中等（Moderate agreement）
- 0.61–0.80: 一致性相當高（Substantial agreement）
- 0.81–1.00: 幾近完全一致（Almost perfect agreement）
（參考資料：Wongpakaran et al., 2013）


## 如何計算

- 線上工具：https://agreestat360.com/ （需註冊帳號）
- R package: `irrCAC`