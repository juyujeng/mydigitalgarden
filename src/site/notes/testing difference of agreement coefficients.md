---
{"dg-publish":true,"permalink":"/testing difference of agreement coefficients/","title":"testing difference of agreement coefficients","tags":["statistics","agreement","reliability","guideline"],"created":"2025-03-18T14:17","updated":"2025-03-18T14:51"}
---


## 檢驗兩組獨立的信度間差異是否顯著

- 情境：比較兩組不同訓練方式的評分者，他們的評分者間信度是否有差異


$$T = \frac{\hat{\kappa}^{2} - \hat{\kappa}^{1}}{\sqrt{V(\hat{\kappa}^{2} - \hat{\kappa}^{1})}}$$
- $\hat{\kappa}^1 =$ 第一組信度（同意度）
- $\hat{\kappa}^2 =$ 第二組信度（同意度）
- $V(\hat{\kappa}^{2} - \hat{\kappa}^{1}) =$ 信度差異的變異數（由於兩個信度獨立，其等於 $v(\hat{\kappa}^1)$ + $v(\hat{\kappa}^2)$）

## 檢驗兩組相關的信度間差異是否顯著

- 情境：比較一組評分者的評分者間信度在受訓前和受訓後是否有差異
- 由於兩組信度非是獨立的，其差異的變異數估計較難。 Gwet (2016)提出利用「linearization」方法估計信度差異的變異數

## online calculator

- https://agreestat.net/agreetest/


## 參考文獻

Gwet, K. L. (2016). Testing the Difference of Correlated Agreement Coefficients for Statistical Significance. _Educational and Psychological Measurement_, _76_(4), 609–637. [https://doi.org/10.1177/0013164415596420](https://doi.org/10.1177/0013164415596420)