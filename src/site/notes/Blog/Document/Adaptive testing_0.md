---
{"dg-publish":true,"permalink":"/Blog/Document/Adaptive testing_0/","title":"三類測驗型式","tags":["blog","CAT","adaptive_testing"],"created":"2023-08-17T00:00:00.000Z","updated":"2023-08-17T12:15"}
---


以下摘要撰寫計畫過程中整理的測驗形式（包含linear test、CAT、MST）摘要，並簡述優、缺點。

值得紀錄的是
1. CAT的優點不只是施測較有效率，同時也可以有較高的測驗準確度。詳細的原因涉及測驗理論，不在此詳述。
2. MST在書中乍看不出優點，但在與研究伙伴討論後想到幾個可能的用法在此記錄。

## Linear test

- 所有受測者回答所有的題目，無論受測者的能力高低以及題目的難度
- 需要大量的題目才能夠用總分準確地測量受測者能力
- 對於能力在母群當中接近平均值的受測者的測量較準確，對能力接近極端值者的能力測量較不準確

## computerized adaptive test (CAT)

- 受測者接受測驗同時估計受測者的能力，利用演算法來決定受測者下一題需回答的題目
- CAT相較於Linear test有兩個優勢
  - 通常較有效率（通常需施測較少之題目）
  - 測量較準確

## multistage test (MST)

- 結合上述兩種測驗形式的特性
- 先測量常規題組（routine test），再根據這一組題目的測量結果選擇後續的測驗題組
- 常規題組可以做為初步篩選，可能可以有幾種用法
    - 利用常規題組將受測者分類（如健康人或是病人），再進行相對應合適的測驗內容
    - 在多能力測驗中，先測量基礎題目，再視受測者表現選擇不同能力之題目

### Table : A comparison of linear, CAT, and MST designs (from Magis et al., 2017, p 4)

#### Linear Test

| Advantages                             | Disadvantages                            |
| -------------------------------------- | ---------------------------------------- |
| Ease of assembly                       | Full length test                         |
| Ease of administration                 | Inefficient for measurement              |
| Least effort for test development (TD) | Inflexible test schedule for test takers |
|                                        | Prone to test copying                    |

#### CAT

| Advantages                             | Disadvantages                           |
| -------------------------------------- | --------------------------------------- |
| Shorter test length                    | Complicated to implement                |
| Efficient for measurement              | Depends on strong model assumptions     |
| Flexible test schedule for test takers | Requires a large calibration data set   |
| Avoids test copying                    | Greatest effort for TD                  |
|                                        | Item exposure more difficult to control |
|                                        | Costly to administer via computer       |
|                                        | Robustness concerns                     |

#### MST

| Advantages                                     | Disadvantages                                      |
| ---------------------------------------------- | -------------------------------------------------- |
| Intermediate test length                       | Depends on model assumptions                       |
| Efficient for measurement                      | Longer than CAT but shorter than linear test       |
| Allows test taker item review (within modules) | Item exposure concerns (similar to CAT)            |
| Easier to implement                            | Costly to administer via computer (similar to CAT) |
| Easier to assemble                             |                                                    |
| Moderate effort for TD                         |                                                    |
| Flexible test schedule for test takers         |                                                    |
| Reduces test copying                           |                                                    |


## references

Magis, D., Yan, D., & Von Davier, A. A. (2017). _Computerized Adaptive and Multistage Testing with R_. Springer International Publishing. [https://doi.org/10.1007/978-3-319-69218-0](https://doi.org/10.1007/978-3-319-69218-0)