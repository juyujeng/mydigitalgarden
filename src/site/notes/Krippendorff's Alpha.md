---
{"dg-publish":true,"permalink":"/Krippendorff's Alpha/","title":"Krippendorff's Alpha","tags":["reliability","guideline","psychometrics"],"created":"2025-01-08T14:55","updated":"2026-01-09T10:21"}
---

Krippendorff's Alpha 是一種評估 **評分者之間一致性** 的統計指標，用於檢測數據的可靠性。它具有以下特點：

1. **適用性廣泛**：
    - 適用於 **不同數據類型**：如名義尺度、順序尺度、區間尺度、比率尺度。
    - 支援 **遣漏值** 處理，不需要丟棄含有遣漏值的數據。
2. **一致性計算的基礎**：
    - 衡量 **觀察一致性** 與 **隨機一致性** 的差異。
    - 計算公式： $\alpha = 1 - \frac{D_o}{D_e}$​​
        - $D_o$​: 觀察到的差異 (Observed Disagreement)
        - $D_e$​: 預期的差異 (Expected Disagreement)

### 判斷切截點

- 可靠：α ≥ .800
- 最低可接受：α ≥ .667

### Krippendorff's Alpha 與 Cohen's Kappa 的差異


| 特點        | **Krippendorff's Alpha**      | **Cohen's Kappa**                |
| --------- | ----------------------------- | -------------------------------- |
| **評分者數量** | 可適用於多位評分者                     | 僅適用於兩位評分者                        |
| **數據類型**  | 名義、順序、區間、比率尺度                 | 主要用於名義尺度（順序尺度需使用weighted  Kappa） |
| **缺失值處理** | 支援處理遺漏值                       | 不支援遺漏值                           |
| **使用場合**  | 通用性較高，適合多種情境                  | 通常用於簡單的二人標記或分類一致性                |
| **計算複雜性** | 較高，需要專門的工具（如 SPSS、R、Python 等） | 計算相對簡單                           |

---

Krippendorff, K. (2004). Reliability in Content Analysis.: Some Common Misconceptions and Recommendations. _Human Communication Research_, _30_(3), 411–433. [https://doi.org/10.1111/j.1468-2958.2004.tb00738.x](https://doi.org/10.1111/j.1468-2958.2004.tb00738.x)