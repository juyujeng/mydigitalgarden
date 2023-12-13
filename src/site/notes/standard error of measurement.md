---
{"dg-publish":true,"permalink":"/standard error of measurement/","title":"standard error of measurement","tags":["terms","psychometric","reliability"],"created":"2023-12-13","updated":"2023-12-13"}
---


# standard error of measurement

- 測量誤差的參數。用來描述重複測量時，測量結果的變異程度（這也算是一種[[reliability\|信度]]的指標。
- 有三種計算方式
1.  $$SEM = \sqrt{\sigma^2_{error}}$$
    - $\sigma^2_{error}$ 是[[intraclass correlation coefficient\|ICC]]中的誤差變異數（error variance）。
    - 可能包含系統性的誤差以及隨機誤差，視計算的[[intraclass correlation coefficient\|ICC]]是agreement或是consistency
2. $$SEM_{difference} = SD_{difference}\sqrt{2}$$
    - $SD_{difference}$ 是對同一個目標的2個不同測量工具（評分者）間的測量結果（評分結果）差值的$SD$。
3. $$SEM = \sigma_y\sqrt{1-ICC} = SD_{pooled}\sqrt{1-ICC}$$
    - 有的人會用同一個工具在不同樣本所報告的$ICC$來使用這個公式計算$SEM$，這樣的做法是錯的。因為不同樣本的變異情況可能有所不同。若要使用這個公式，務必先用自己的樣本先計算$ICC$。

## 參考文獻

De Vet, H., Terwee, C., Mokkink, L., & Knol, D. (2011). Reliability. In _Measurement in Medicine: A Practical Guide_ (Practical Guides to Biostatistics and Epidemiology, pp. 96-149). Cambridge: Cambridge University Press. doi:10.1017/CBO9780511996214.006