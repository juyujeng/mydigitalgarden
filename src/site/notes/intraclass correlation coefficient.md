---
{"dg-publish":true,"permalink":"/intraclass correlation coefficient/","title":"intraclass correlation coefficient","tags":["terms","reliability","guideline","statistics"],"created":"2024-05-28T09:57","updated":"2024-05-28T23:33"}
---


## 說明

Intraclass correlation coefficient (ICC)是一個被廣泛使用的信度指標。它可以被使用在再測信度、評分者間信度以及評分者內信度。它可以反應多個測量（評分）結果的**相關**（correlation）或**同意**（agreement）程度。

ICC包含多個不同種類（form），Shrout 與 Fleiss（1979）提出6種，而McGraw與Wong（1996）提出10種。根據Koo與Li（2016）的整理，這些不同種類詳列如[[#ICC 種類表]]。仔細看可以發現，某些不同類的ICC計算的公式是一樣的。以McGraw與Wong（1996）的架構為例，常用的 Two-way random effects, absolute agreement, single rater/measurement 和 Two-way mixed effects, absolute agreement, single rater/measurement 計算結果是相同的。

研究者應根據研究目的選擇適合的種類。Koo與Li（2016）依照McGraw與Wong（1996）的分類概念提出[[#ICC選擇流程圖]]，按照以下4個問題的答案進行選擇：

1. 是否所有的被評分樣本都是被同一組的評分者所評分？Do we have the same set of raters for all subjects?
2. 評分者樣本是從某個大群體中隨機選取的，還是特定的評分者樣本？Do we have a sample of raters randomly selected from a larger population or a specific sample of raters?
3. 我們關注的是各個評分者的信度，還是多個評分者平均值的信度？Are we interested in the reliability of single rater or the mean value of multiple raters?
4. 我們關心的是一致性還是同意度？Do we concern about consistency or agreement?

## 結果解釋

依據Koo與Li（2016）

| ICC Value  | Reliability           |
| ---------- | --------------------- |
| < 0.5      | Poor reliability      |
| 0.5 - 0.75 | Moderate reliability  |
| 0.75 - 0.9 | Good reliability      |
| > 0.9      | Excellent reliability |

## R程式碼

### psych package

`psych::ICC`計算是按照Shrout 與 Fleiss（1979）的架構，結果會得到6種ICC的結果。

```r
library(psych)
ICC(x, missing=TRUE, alpha=.05, lmer=TRUE, 
    check.keys=FALSE)
```

### irr package

`irr::icc`的計算則是按照McGraw與Wong（1996）的架構，需要設定`model`、`type`、`unit`。

```r
library(irr)
icc(ratings, model = c("oneway", "twoway"), 
    type = c("consistency", "agreement"), 
    unit = c("single", "average"), r0 = 0,
    conf.level = 0.95)
```

## 附錄

### ICC 種類表

| McGraw and Wong (1996) Convention                                        | Shrout and Fleiss (1979) Convention | Formulas for Calculating ICC                                        |
| ------------------------------------------------------------------------ | ----------------------------------- | ------------------------------------------------------------------- |
| One-way random effects, absolute agreement, single rater/measurement     | ICC (1,1)                           | $\frac{MS_R - MS_W}{MS_R + (k + 1)MS_W}$                            |
| Two-way random effects, consistency, single rater/measurement            | -                                   | $\frac{MS_R - MS_E}{MS_R + (k - 1)MS_E}$                            |
| Two-way random effects, absolute agreement, single rater/measurement     | ICC (2,1)                           | $\frac{MS_R - MS_E}{MS_R + (k - 1)MS_E + \frac{k}{n}(MS_C - MS_E)}$ |
| Two-way mixed effects, consistency, single rater/measurement             | ICC (3,1)                           | $\frac{MS_R - MS_E}{MS_R + (k - 1)MS_E}$                            |
| Two-way mixed effects, absolute agreement, single rater/measurement      | -                                   | $\frac{MS_R - MS_E}{MS_R + (k - 1)MS_E + \frac{k}{n}(MS_C - MS_E)}$ |
| One-way random effects, absolute agreement, multiple raters/measurements | ICC(1,k)                            | $\frac{MS_R - MS_W}{MS_R}$                                          |
| Two-way random effects, consistency, multiple raters/measurements        | -                                   | $\frac{MS_R - MS_E}{MS_R}$                                          |
| Two-way random effects, absolute agreement, multiple raters/measurements | ICC (2,k)                           | $\frac{MS_R - MS_E}{MS_R + \frac{MS_C - MS_E}{n}}$                  |
| Two-way mixed effects, consistency, multiple raters/measurements         | ICC (3,k)                           | $\frac{MS_R - MS_E}{MS_R}$                                          |
| Two-way mixed effects, absolute agreement, multiple raters/measurements  | -                                   | $\frac{MS_R - MS_E}{MS_R + \frac{MS_C - MS_E}{n}}$                  |

說明：
$MS_R$: mean square for rows; $MS_W$: mean square for residual sources of variance; $MS_E$: mean square for error; $MS_C$: mean square for columns; $n$: number of subjects; $k$: number of raters/measurements

### ICC選擇流程

![Pasted image 20240528103949.png|來源：Koo & Li (2016)](/img/user/Pasted%20image%2020240528103949.png)
