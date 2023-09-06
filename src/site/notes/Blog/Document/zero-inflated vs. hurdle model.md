---
{"dg-publish":true,"permalink":"/Blog/Document/zero-inflated vs. hurdle model/","title":"zero-inflated vs. hurdle model","tags":["blog","count","statistics"],"created":"2022-01-04T00:00:00.000Z","updated":"2023-09-06T00:00:00.000Z"}
---


# zero-inflated vs. hurdle model

[[statistics/count data/zero-inflated model\|zero-inflated model]]和[[statistics/count data/hurdle model\|hurdle model]]都是在處理count data有大量的0的時候常用的方法。

這兩種方法的結果也長得很像，都有一個針對多有可能為0的zero part，以及一個針對大於0的數字估計的count part。在文獻上兩種方法出來的結果適配度也很常是差不多的，有時候前者好一點，有時候後者好一點。

兩者主要的區分在於對0的概念上。zero-inflated model的假設中0可能有兩種分配的來源（zero part以及count part兩個分配），而hurdle model則假設0只來自zero part的那個binary分配。有的人是這麼說的，zero-inflated model的0可能包含真的0（這事件本來就不會發生，由zero part來估計）以及取樣的0（有可能會發生，但是剛好取樣到0，由count part來估計）。

因此，在選擇要使用哪一種時，如果適配結果都差不多，就要傷點腦筋想一下，資料的0到底是不是可能來自兩種不同的分配，因為在結果的解讀上是不同的概念。

另一方面，如果資料的0的次數比預期少（zero deflation）時，目前只有hurdle model可以處理，而zero-inflated model無法處理這種情況。
