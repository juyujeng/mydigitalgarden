---
{"dg-publish":true,"permalink":"/Different types of Kappa values/","title":"Different types of Kappa values","tags":["guideline","kappa","reliability","validity","statistic"],"created":"2024-09-24T15:38","updated":"2024-10-25T14:56"}
---


Different types of kappa coefficients are used to assess inter-rater reliability, each tailored to specific contexts and data types. Here’s a summary of the key differences among various kappa values:

## Cohen's Kappa

- **Purpose**: Measures agreement between two raters for categorical items.
- **Use Case**: Ideal for dichotomous (two-category) classifications.
- **Calculation**: It accounts for the proportion of observed agreement minus the proportion of agreement expected by chance.
- **Interpretation**: Values range from -1 (complete disagreement) to 1 (perfect agreement), with 0 indicating no agreement beyond chance. Guidelines suggest:
	- < 0.00: Poor agreement
	- 0.00 - 0.20: Slight agreement
	- 0.21 - 0.40: Fair agreement
	- 0.41 - 0.60: Moderate agreement
	- 0.61 - 0.80: Substantial agreement
	- > 0.80: Almost perfect agreement [2].

## Fleiss' Kappa

- **Purpose**: Extends Cohen's kappa for multiple raters.
- **Use Case**: Suitable for assessing agreement among three or more raters classifying items into categories.
- **Calculation**: Similar to Cohen's but adjusts for the number of raters and categories, providing a more comprehensive view of reliability across multiple observers.
- **Interpretation**: The same scale as Cohen's kappa applies, but it can handle more complex scenarios involving multiple raters.

## Watson's Kappa

- **Purpose**: A variation designed to address specific issues in the calculation of kappa.
- **Use Case**: Often used in psychological and educational testing where the data may not fit traditional assumptions of independence.
- **Calculation**: It modifies the standard kappa formula to better reflect situations where rater independence is questionable.

## PABAK (Prevalence-Adjusted and Bias-Adjusted Kappa，PABAκ)

- **Purpose**: Addresses limitations of Cohen's kappa, particularly in cases with imbalanced categories.
- **Use Case**: Useful when the prevalence of categories is unequal or when there is a significant bias in rater classifications.
- **Calculation**: Adjusts the expected agreement based on the prevalence of categories, providing a more accurate reflection of rater agreement under these conditions.
- **Interpretation**: Similar interpretation guidelines as Cohen's kappa, but offers a clearer picture in skewed distributions.

## Altman's Kappa

- **Purpose**: A variant that also considers the weighting of disagreements based on their severity.
- **Use Case**: Particularly useful in clinical settings where some disagreements may be more critical than others.
- **Calculation**: It incorporates weights into the kappa calculation, allowing for differentiation between types of disagreement.
- **Interpretation**: Like other kappas, it ranges from -1 to +1, but provides nuanced insights into the nature of disagreements.

### Summary Table

| Kappa Type     | Number of Raters | Use Case                    | Key Feature                            |
| -------------- | ---------------- | --------------------------- | -------------------------------------- |
| Cohen's Kappa  | 2                | Dichotomous classifications | Basic measure of agreement             |
| Fleiss' Kappa  | ≥3               | Multiple raters             | Extends Cohen's for multiple observers |
| Watson's Kappa | Varies           | Psychological testing       | Adjusts for non-independence           |
| PABAK          | Varies           | Imbalanced categories       | Adjusts for prevalence and bias        |
| Altman's Kappa | Varies           | Clinical settings           | Weights disagreements by severity      |

These variations provide researchers with tools suited to different types of data and research questions, enhancing the assessment of reliability across diverse fields.

Citations:
[1] <https://link.springer.com/article/10.1007/s11634-020-00394-8>
[2] <https://en.wikipedia.org/wiki/Cohen%27s_kappa>
[3] <https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9517543/>
[4] <https://www.scribbr.com/methodology/types-of-validity/>
[5] <https://onlinelibrary.wiley.com/doi/full/10.1002/sim.7679>
[6] <https://online.stat.psu.edu/stat504/lesson/11/11.2/11.2.4>
[7] <https://www.ncbi.nlm.nih.gov/books/NBK531518/table/ch3.tab1/>
[8] <https://academic.oup.com/ptj/article/85/3/257/2805022>
