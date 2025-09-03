---
{"dg-publish":true,"permalink":"/statistics/Interater reliability/","title":"Interater reliability","tags":["docs","reliability","agreement","nominal","statistics"],"created":"2022-09-29","updated":"2025-08-01T22:13"}
---


|                | kappa   | weighted kappa | Tetrachoric Correlation Coefficient | Intraclass correlation coefficient |
| -------------- | ------- | -------------- | ----------------------------------- | ---------------------------------- |
| Variable scale | nominal | nominal        | nominal                             | nominal, ordinal                   |
| Raters         | 2       | 2              | 2                                   | 2+                                 |



# kappa family

VarScale: 'nominal scale'
Raters: 2

## Cohen's kappa

延伸自Scott (1959)，同樣校正了因為機率而剛好一致猜測。

$$\kappa = \frac{p_o - p_c}{1 - p_c}$$

其中，$p_o$是觀測到一致的比率，而$p_c$則是亂猜時剛好一致的機率。

這個算法在contigency table當中，就只看對角線（一致的部份）。

### levels of agreement

|  $\kappa$   |  levels   |
|:-----------:|:---------:|
|   > 0.75    | excellent |
| 0.40 ~ 0.75 |   good    |
|    < 0.4    |   poor    |


## Weighted Kappa

在分類的時候，某些類別分類的不一致導致的後果，可能會比其他類別分類的不一致嚴重。例如在進行心理疾患的診斷時，一個病人是精神官能症（neurosis）還是思覺失調（psychos），這個分類的錯誤跟是精神官能症或是人格疾患（personality disorder）的分類錯誤比起來就嚴重得多。

在本來的[[statistics/Interater reliability\|Interater reliability]]當中，所有的不一致都是等價的。而在weighted kappa當中，則會預先設定好各個類別不一致時的權重，例如

| raters     | category A | category B | category C |
|:---------- |:----------:|:----------:|:----------:|
| category A |     0      |     1      |     2      |
| category B |     1      |     0      |     1      |
| category C |     2      |     1      |     0      |

若是將A錯分為B，不一致權重為1，但若A錯分為C，不一致的權重為2。代表錯分A為C比錯分A為B還要嚴重。

## PABAK (Prevalence-Adjusted and Bias-Adjusted Kappa)

- **Purpose**: Addresses limitations of Cohen's kappa, particularly in cases with imbalanced categories.
- **Use Case**: Useful when the prevalence of categories is unequal or when there is a significant bias in rater classifications.
- **Calculation**: Adjusts the expected agreement based on the prevalence of categories, providing a more accurate reflection of rater agreement under these conditions.
- **Interpretation**: Similar interpretation guidelines as Cohen's kappa, but offers a clearer picture in skewed distributions.

## Summary Table

| Kappa Type     | Number of Raters | Use Case                    | Key Feature                            |
| -------------- | ---------------- | --------------------------- | -------------------------------------- |
| Cohen's Kappa  | 2                | Dichotomous classifications | Basic measure of agreement             |
| Fleiss' Kappa  | ≥3               | Multiple raters             | Extends Cohen's for multiple observers |
| Watson's Kappa | Varies           | Psychological testing       | Adjusts for non-independence           |
| PABAK          | Varies           | Imbalanced categories       | Adjusts for prevalence and bias        |
| Altman's Kappa | Varies           | Clinical settings           | Weights disagreements by severity      |


## how to perform kappa

R軟體當中有數個套件都可以計算$\kappa$，包含了`psych::cohen.kappa`、`vcd::Kappa`，前者計算時要輸入原始資料，而後者則是輸入contigency table。


# Tetrachoric Correlation Coefficient

用在二分變項的分類的一致性上。假設二分變項的分類背後有一個潛在的連續向度，因此這個潛在變項的強度以及分類的切截點會影響著錯誤分類的機率，也就是說，分錯不會是隨機的，會受到要分類的目標在該潛在向度上的訊號強度影響。

適用在分類的時機符合背後有連續變項的假設，例如看醫學影像判斷是否有腫瘤。

# Intraclass correlation coefficient

$$ICC = \frac{variance of interest}{total variance}$$

## types of ICC

### ICC1 = ICC(1,1) = 1 way random

$$ICC = \frac{\sigma^2_{treat}}{\sigma^2_{treat} + \sigma^2_{residual}}$$

適用在所有的目標被1組隨機選取的raters評量，每個評分者可以只評部份的目標。

## absolute agreement or consistency

- absolute agreement: 分類是否一致（nominal scale）
- consistency: 評分的高低是否方向一致（ordinal scale）

## choose between ICCs

| ![Pasted image 20220930111639.png](/img/user/statistics/Pasted%20image%2020220930111639.png) |
| :----------------------------------- |
| A flowchart showing the selection process of the ICC form based on the experimental design of a reliability study. (Koo & Li, 2016)                                     |

## levels of reliability

(Koo & Li, 2016)

- < 0.50: Poor reliability
- 0.5 ~ 0.75: Moderate reliability
- 0.75 ~ 0.9: Good reliability
- \> 0.9: Excellent reliability

## how to perform ICC

R軟體當中有數個套件都可以計算$ICC$，包含了`psych::ICC`、`irr::icc`，前者計算時要輸入原始資料，而後者則是輸入contigency table。

# references

Banerjee, M., Capozzoli, M., McSweeney, L., & Sinha, D. (1999). Beyond kappa: A review of interrater agreement measures. Canadian Journal of Statistics, 27(1), 3–23. https://doi.org/10.2307/3315487

Koo, T. K., & Li, M. Y. (2016). A Guideline of Selecting and Reporting Intraclass Correlation Coefficients for Reliability Research. Journal of Chiropractic Medicine, 15(2), 155–163. https://doi.org/10.1016/j.jcm.2016.02.012

Liljequist, D., Elfving, B., & Skavberg Roaldsen, K. (2019). Intraclass correlation – A discussion and demonstration of basic features. PLOS ONE, 14(7), e0219854. https://doi.org/10.1371/journal.pone.0219854

https://www.agreestat.com/
