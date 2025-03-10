---
{"dg-publish":true,"permalink":"/Gewt's AC/","title":"Gewt's AC","tags":["agreement","reliability","guideline","statistics"],"created":"2025-03-10T23:05","updated":"2025-03-10T23:51"}
---


## Kappa paradox

Kappa paradox 指 Cohen's kappa 在某些情況下，可能發生兩位評分者的評分一致百分比（percentage of agreement）和 Cohen's kappa 結果差異很大的情況。例如一致百分比高，但是 Cohen's kappa低；或是一致百分比低而 Cohen's kappa 高。

## 發生Kappa paradox的情境

- 邊際總數不平衡：當列聯表 (contingency table) 的邊緣總數（即行總和或列總和）存在嚴重不平衡時，即使觀察到高 agreement，Kappa 值也可能大幅降低。這種情況在實際研究中經常發生，特別是在某個（或某些）分類結果觀察到的次數遠高於其他分類結果觀察到的次數時。
    - 例如：如下表所示，兩個評分者評分為1的情況遠高於評分為0或2

| Rater 2 \ Rater 1 | 0 | 1  | 2  | **總計** |
|--------------------|---|----|----|-----------|
| 0                  | 0 | 0  | 0  | 0         |
| 1                  | 0 | 29 | 0  | 29        |
| 2                  | 0 | 1  | 0  | 1         |
| **總計**           | 0 | 30 | 0  | 30        |

- 邊際分佈呈不對稱：指列聯表對角線以外的數值分佈不均勻。這可能跟評分者的評分能力有偏誤（bias），或是某個分類結果的盛行率（prevalence）很高（或很低）有關。
    - 例如：如下表所示

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

## 如何計算

- 線上工具：https://agreestat360.com/
- R package: `irrCAC`