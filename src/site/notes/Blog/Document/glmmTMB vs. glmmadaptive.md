---
{"dg-publish":true,"permalink":"/Blog/Document/glmmTMB vs. glmmadaptive/","title":"glmmTMB vs. GLMMadaptive","tags":["blog","R/packages"]}
---


# glmmTMB vs. GLMMadaptive

記錄一下分析資料時使用`glmmTMB`以及`GLMMadaptive`的心得

|      | `glmmTMB`                                       | `GLMMadaptive`                                     |
| ---- | ----------------------------------------------- | -------------------------------------------------- |
| 估計方法 | Laplace approximation                           | adaptive Gauss-Hermite quadrature                  |
| 預測值  | 可以進行單純count part預測、zero part預測，以及兩部份模型加起來的期望值預測 | 沒辦法只進行count part預測，只能做zero part預測，以及兩部份模型加起來的期望值預測 |


估計方法的差異在本次zero-inflated model使用過程中有很大的使用經驗差異。`glmmTMB`比較常出現convergent problem，而`GLMMadaptive`幾乎沒有。根據`glmmTMB`的troubleshooting說明，會出現問題主要是和random effect有關，如果拿掉zero part random intercept就不會再跳出錯誤訊息了。而根據`GLMMadaptive`做的模型比較，有沒有zero part random intercept其實沒有顯著的差異。因此如果不強求一定要納入zero part random intercept，兩個packages的結果是一致的。不過如果一定要納入zero part random intercept，那就只能使用`GLMMadaptive`才不會有錯誤警告出現。


兩個套件的另一個差異是在進行預測（predict）時，`glmmTMB`可以只根據count part的結果進行預測，而`GLMMadaptive`不行。會有這個需求是因為很常只有count part的預測變項有顯著的結果，但是zero part沒有顯著的預測變項，因此若只想要看count part的預測線時，`GLMMadaptive`沒辦法給我這個結果[^1]。

文獻上討論Laplace approximation和adaptive Gauss-Hermite quadrature哪一種估計方法比較準的有好幾篇，我大概看了一下他們的結論，其實不同研究的結果並不一致[^2]。

另一個使用上的差異是在安裝上，`GLMMadaptive`安裝比較沒有什麼問題。但是`glmmTMB`因為還需要`TMB`，有時候在更新套件時會有版本不一致的情況，有點小困擾。

[^1]: 也許`emmeans::qdgr()`可以，但需要試試看
[^2]: 不過`glmmTMB`的作者在他的[網頁](https://bbolker.github.io/mixedmodels-misc/glmmFAQ.html#should-i-treat-factor-xxx-as-fixed-or-random)上提到，Gauss-Hermite quadrature比Laplace approximation還要準確，但是估計速度比較慢（但在我的資料感覺不出來），而且random effect的數量上限制比較多。