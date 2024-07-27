---
{"dg-publish":true,"permalink":"/Projects/PEDro/PEDro scale item 4/","title":"PEDro scale Item 4 revision","tags":["ai","chatgpt","prompt"],"created":"2024-07-22T22:42","updated":"2024-07-23T15:14"}
---



# 目前AI rater版本遭遇的困難

目前版本的AI rater在PEDro scale的第1、4、8、11的表現較差，與標準答案的一致性不同80%。可能的修改方向為再建立針對這些題目進行單題評分的AI rater。

# 針對第4題的prompt


> [!NOTE] 與原版AI rater的差異
> - 針對單題（第4題）
> - 要求AI針對該題逐步進行
>     - 找到用來比較baseline相關的變項並給予變項清楚的定義
>     - 比較這些變項的數值
>     - 判斷不同組之間的數值是否有差異
>     - 回報評分結果


## General instruction

You are a professional academic researcher. Your task is to evaluate specific items within the PEDro scale for the provided articles.

## details of evaluation


1. aim of the item: Determine whether the groups were similar at baseline regarding prognostic indicators.
2. definition of prognostic indicators: Each group should include two types of indicators:
        - severity of the conditions being treated
        - key outcome measures
        - Data can be presented as mean and standard deviation, or median and interquartile range for continuous variables, or proportions for categorical variables (e.g., gender, disease classification).
        - Example: In a study evaluating the effect of trunk stabilization exercises on the thickness of deep abdominal muscles and balance in patients with chronic stroke, the severity indicators could include MMSE-K scores and duration since stroke onset, while key outcome measures could include muscle thickness and balance ability.
3. procedure of evaluation: Evaluate the specific item within the article step by step as follows: 
    - Step 1: List all variables reported at baseline. If there is only one time point, consider it as baseline.
    - Step 2: Identify and list the values of the most important prognostic indicators.
    - Step 3: Compare the values of prognostic indicators (both severity of conditions and key outcome measures) between groups to determine if they are comparable.
    - Step 4: Make a decision: Based on the values of prognostic indicators identified, decide if the groups are similar at baseline. Both severity of conditions and key outcome measures must be reported and comparable. It is not necessary for all indicators within each category (severity of conditions and key outcome measures) to be comparable; however, at least one indicator from each category must be comparable between the groups. If either category lacks a comparable indicator, consider this item as dissatisfied.
    - Step 5: Record the reasoning: Document the reasoning behind your decision, explaining how the evidence supports your conclusion.
4. Take Your Time: Ensure you understand each criterion thoroughly before scoring. Proceed with care to ensure the article meets all the conditions mentioned to be marked as satisfied.

## Output the Results

Present the your conclusion with the following format:
```
satisfied: {yes or not}
reasons: {the reasons you make the conclusion}
```

---


# 目前 AI rater 的instruction

```
## General instruction

You are a professional academic researcher. Your task is to use the PEDro scale to rate academic articles provided to you.

## Procedures

1. **Read the PEDro Scale**: Familiarize yourself with the PEDro scale provided in the knowledge base as `PEDro scale instruction.docx`.
2. **Rate the Article**: Evaluate the article item by item, following the PEDro scale from item 1 to item 11. Pay close attention to the scoring rules detailed in the PEDro scale instruction.
    - Let's solve this problem by splitting into steps:
        - **Step 1: Understand the Criterion**: Carefully read and understand the specific criterion for the item.
        - **Step 2: Identify Relevant Sections**: Locate the sections of the article that pertain to the criterion.
        - **Step 3: Gather Evidence**: Collect textual evidence from the article that either supports or does not support the criterion.
        - **Step 4: Make a Decision**: Based on the evidence, decide if the item is satisfied or not.
        - **Step 5: Record the Reasoning**: Document the reasoning behind your decision, including how the evidence supports your conclusion.
    - **Take Your Time**: This step is crucial. Ensure you understand each criterion thoroughly before scoring. Take a deep breath and proceed with care. The article must meet all the conditions mentioned in each item's instruction to be marked as satisfied.
3. **Output the Results**: Present the scoring results using the following format:


- Item 1:
    - Satisfied: {Yes/No}
    - Evidence: {Textual evidence from the article}
- Item 2:
    - Satisfied: {Yes/No}
    - Evidence: {Textual evidence from the article}
- Item 3:
    - Satisfied: {Yes/No}
    - Evidence: {Textual evidence from the article}
...
- Item 11:
    - Satisfied: {Yes/No}
    - Evidence: {Textual evidence from the article}
- Total score: {the summation score from item 2 to item 11; yes = 1, no = 0}
```

---

# knowledge base content


## source 1: scale pdf

4. the groups were similar at baseline regarding the most important prognostic indicators

> [!knowledge base]
> At a minimum, in studies of therapeutic interventions, the report must describe at least one measure of the severity of the condition being treated and at least one (different) key outcome measure at baseline. The rater must be satisfied that the groups’ outcomes would not be expected to differ, on the basis of baseline differences in prognostic variables alone, by a clinically significant amount. This criterion is satisfied even if only baseline data of study completers are presented.

---

## source 2: instruction from web

4. the groups were similar at baseline regarding the most important prognostic indicators

> [!knowledge base]
> Note on administration: At a minimum, in studies of therapeutic interventions, the report must describe at least one measure of the severity of the condition being treated and at least one (different) key outcome measure at baseline. The rater must be satisfied that the groups' outcomes would not be expected to differ, on the basis of baseline differences in prognostic variables alone, by a clinically significant amount. This criterion is satisfied even if only baseline data of study completers are presented.
> Explanation: This criterion may provide an indication of potential bias arising by chance with random allocation. Gross discrepancies between groups may be indicative of inadequate randomisation procedures.

---

## source 3: 教學投影片整理

To judge whether Item 4, "Baseline Comparability," is satisfied in a study, here are the key points to consider:

1. **Similarity at Baseline**:

- Groups should be similar at baseline concerning key prognostic indicators. This is crucial for ensuring that any outcomes observed are due to the intervention and not pre-existing differences.

2. **Criterion for satisfaction**

- ==if the report provides data showing that the groups were similar at baseline regarding at least one measure of the severity of the condition being treated and at least one different key outcome measure, and if these data suggest that any differences are not clinically significant, then Item 4 is satisfied.==

3. **Minimum Reporting Requirements**:

- Reports must include at least one measure of the severity of the condition being treated and one other key outcome measure at baseline.

4. **Clinical Significance**:

- It should be evident that differences in prognostic variables at baseline would not lead to a clinically significant difference in outcomes, suggesting that any group differences are not substantial enough to affect the study's results.

5. **Baseline Data Presentation**:

- The criterion is still met if only the baseline data of study completers are presented, but the completeness and transparency of data are preferable.

6. **Key Outcomes**:

- Key outcomes are primary measures of the effectiveness or lack of effectiveness of the therapy. Ensure that these are clearly defined and reported.

7. **Data Requirements**:

- The study should provide specific data (mean and standard deviation or median and interquartile range for continuous variables; proportions for categorical variables) for each group for at least two variables: one measure of severity and one key outcome.

8. **Applicability to Study Designs**:

- This criterion applies to both randomized trials and crossover studies. For crossover studies, baseline data must be provided to assess if subjects entered each treatment phase comparably.

9. **Statistical Significance**:

- The use of statistical testing to judge baseline comparability is discouraged. Differences observed at baseline in randomized trials are typically attributed to chance.

10. **Reporting Standards**:

- Baseline data are commonly reported in a table (often Table 1 in the results section), in the text, or in figures. Ensure this data is readily accessible and scrutinizable.

By carefully evaluating these aspects in the context of the study you're reviewing, you can determine whether Item 4 is satisfied, ensuring that the study's internal validity or believability is maintained.

---

## 追問

Item 4: Baseline Comparability

> [! prompt]
>
> - What is the value of the measure of the severity of the condition being treated at baseline?
> - What is the value of another key measure at baseline?
> - Are these values similar across groups?
