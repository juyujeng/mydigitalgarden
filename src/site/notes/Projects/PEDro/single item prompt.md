---
{"dg-publish":true,"permalink":"/Projects/PEDro/single item prompt/","title":"single item prompt","tags":["prompt","ai","chatgpt"],"created":"2024-07-26T16:36","updated":"2025-08-05T14:35"}
---


# General instruction
You are a professional scientific researcher. Your task is to evaluate the quality of the medical research provided to you. Follow the detailed instructions below carefully. If you do it right, I'll tip you $1000.

# Basic prompt




## Item 6: Blinding of All Therapists


### Details of evaluation

- Aim of evaluation: Determine whether the therapists who administer the therapy are unaware of the treatment group assignment for each subject.
- Criterion for satisfaction: 
    1. Therapists are considered blinded if they cannot discern whether individual subjects received the treatment or a control.
- Considerations for evaluation:
    - Methods for Blinding: Techniques such as the use of sealed opaque envelopes, central telephone systems, or web-based systems are common methods to ensure blinding. For trials involving complex interventions where blinding might be challenging (like exercise programs or surgeries), the methodology needs to be clearly articulated to see if blinding was feasible.
    - Complex Interventions: In trials with interventions that cannot be blinded, such as some surgical procedures or physical therapies, the reports must articulate how they managed potential biases.
    - Reporting: Information about blinding is typically detailed in the methods section and can be crucial for understanding how bias was managed in the study.
    - Challenges with Terminology: Terms like "single-blind," "double-blind," or "triple-blind" are often used ambiguously, so detailed descriptions of who was blinded and how are essential for proper evaluation.

- Examples:
    - satisfied:
        - The clinical practitioners who applied the conventional intervention and those who administered the baseline, postintervention, and follow-up clinical assessments to the intervention groups were blinded.
    - not satisfied: 
        - not mentioned any thing about blinding of therapists.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


## Item 7: Blinding of All Assessors


### Details of evaluation

- Aim of evaluation: Determine whether the assessors are unaware of the treatment group assignment for each subject.
- Criterion for satisfaction: 
    1. The study must explicitly state in the methods that assessors were unaware of which group subjects were allocated to. In cases where key outcomes are self-reported, the subject is the assessor, and they must be blinded. This blinding of assessors, whether they are subjects providing self-reports or external raters, must be clearly described in the methodology.
- Considerations for evaluation:
    - Methods for Blinding: Techniques such as the use of sealed opaque envelopes, central telephone systems, or web-based systems are common methods to ensure blinding. For trials involving complex interventions where blinding might be challenging (like exercise programs or surgeries), the methodology needs to be clearly articulated to see if blinding was feasible.
    - Complex Interventions: In trials with interventions that cannot be blinded, such as some surgical procedures or physical therapies, the reports must articulate how they managed potential biases.
    - Reporting: Information about blinding is typically detailed in the methods section and can be crucial for understanding how bias was managed in the study.
    - Challenges with Terminology: Terms like "single-blind," "double-blind," or "triple-blind" are often used ambiguously, so detailed descriptions of who was blinded and how are essential for proper evaluation.
- Examples:
    - satisfied:
        - all of the out-come measures were administered to the patients by the same blinded assessor.
    - not satisfied: 
        - This was a randomized controlled trial with no assessor blinding.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```



## Item 8: adequate follow up



### Details of evaluation

- Aim of evaluation: Determine whether this research has adequate follow-up data points.
- Criterion for satisfaction: 
    1. Subject Reporting: The report must explicitly state:
        - The number of subjects initially allocated to groups.
        - The number of subjects from whom key outcome measures were obtained.
    2. Follow-Up Completeness:
        - The overall follow-up completeness is considered satisfactory if measures of at least one key outcome were obtained from more than 85% of the total subjects initially allocated to all groups combined.
        - This means the total loss rate should be less than 15%.
        - If the initial number of participants included and the numbers of participants who completed the study are not well documented, this criterion is not satisfied.
- Examples:
    - satisfied:
        - The study randomly assigned 48 individuals to 3 groups, with 16 people per group. All 16 participants in each group completed the study and their data were analyzed, resulting in a 100% retention rate (48/48 = 1).
    - not satisfied: 
        - The number of subjects initially allocated to groups and the number of subjects from whom key outcome measures were obtained were not both reported.
        - The follow-up rate for at least one group is less than 85%. For example, if the number of subjects from whom key outcome measures were obtained divided by the number of subjects initially allocated to the group is less than 0.85.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


## Item 9: intention to treat analysis


### Details of evaluation

- Aim of evaluation: Determine whether the study uses an Intention to Treat (ITT) analysis to maintain the integrity of random allocation and minimize bias.
- Definition of Intention to Treat Analysis:
    - Intention to treat (ITT) analysis involves analyzing data as if all subjects received the treatment or control condition they were initially allocated, regardless of what actually occurred during the trial. This approach accounts for protocol deviations and maintains the random allocation balance, thereby minimizing bias.
- Criterion for satisfaction: 
    1. The criterion is met if the study explicitly states that an ITT analysis was used. Alternatively, the study can fulfill this requirement if it reports that all subjects received the treatment or control conditions as initially allocated, or that subjects were analyzed according to their initial group allocation.
- Examples:
    - satisfied:
        - An intention-to-treat analysis was performed.
    - not satisfied: 
        - The analysis was conducted using a per-protocol approach, where only participants who completed the study according to the specified treatment protocol were included in the final evaluation. As a result, individuals who dropped out or did not adhere to the assigned treatment were excluded from the analysis.

### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


## Item 10: between-group statistical comparison


### Details of evaluation

- Aim of evaluation: Determine whether the study provides results of statistical comparisons between groups for key outcomes.
- Criterion for satisfaction: 
    1. The study must report results of between-group statistical comparisons for at least one key outcome. This can include comparisons of outcomes measured after treatment administration or comparisons of changes over time between groups. The comparisons may involve hypothesis testing (e.g., providing a p-value) or providing estimates (e.g., mean or median differences, differences in proportions, number needed to treat, relative risk, or hazard ratio) along with their confidence intervals.
- Examples:
    - satisfied:
        - Between- group analyses revealed significant differences and large effects among the three groups...
    - not satisfied: 
        - The study only present the differences between different time points within group, but not showed any comparisons between group.

### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```




## Item 11: Point estimates and variability


### Details of evaluation

- Aim of evaluation:  Determine whether the study reports point measures and measures of variability for at least one key outcome.
- Definitions
    - Point Measure: A measure of the size of the treatment effect, described as a difference in group outcomes or as the outcome in each group.
    - Measures of Variability: Statistical measures that describe the variability of the data, including:
        - Standard Deviations (SDs)
        - Standard Errors (SEs)
        - Confidence Intervals (CIs)
        - Interquartile Ranges (IQRs)
        - Ranges
- Criterion for Satisfaction
    1. The study must report point measures of the treatment effect, which can be described as a difference in group outcomes or as the outcome in each group.
    2. The study must include measures of variability, such as SDs, SEs, CIs, IQRs, or ranges.
    3. Point measures and/or measures of variability may be provided graphically (e.g., error bars in a figure) as long as it is clear what is being graphed and what the error bars represent (e.g., SDs or SEs).
    4. For categorical outcomes, this criterion is satisfied if the number of subjects in each category is given for each group.
### Examples:
- satisfied:
    - The study present mean (SD)  for each group on key outcome measure.
- not satisfied: 
    - The study present mean (SD)  for each group on participants' demographic variables but not on key outcome measure.

### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


# CoT prompt

## Item 6

### Details of evaluation

- Aim of evaluation: Determine whether the therapists who administer the therapy are unaware of the treatment group assignment for each subject.
- Criterion for satisfaction: 
    1. Therapists are considered blinded if they cannot discern whether individual subjects received the treatment or a control.
- Considerations for evaluation:
    - Methods for Blinding: Techniques such as the use of sealed opaque envelopes, central telephone systems, or web-based systems are common methods to ensure blinding. For trials involving complex interventions where blinding might be challenging (like exercise programs or surgeries), the methodology needs to be clearly articulated to see if blinding was feasible.
    - Complex Interventions: In trials with interventions that cannot be blinded, such as some surgical procedures or physical therapies, the reports must articulate how they managed potential biases.
    - Reporting: Information about blinding is typically detailed in the methods section and can be crucial for understanding how bias was managed in the study.
    - Challenges with Terminology: Terms like "single-blind," "double-blind," or "triple-blind" are often used ambiguously, so detailed descriptions of who was blinded and how are essential for proper evaluation.

### Steps for Evaluation:

1. **Check for Blinding Information**: Review the research documentation to identify if it explicitly states that the therapists administering the therapy were blinded to the treatment group assignments.
2. **Evaluate the Blinding Description**: Ensure that the description of blinding specifies that the therapists did not know whether subjects received the treatment or a control.
3. **Document Findings**: Note whether the blinding of therapists is explicitly mentioned and described.

### Examples:
- satisfied:
    - The clinical practitioners who applied the conventional intervention and those who administered the baseline, post intervention, and follow-up clinical assessments to the intervention groups were blinded.
- not satisfied: 
    - not mentioned any thing about blinding of therapists.
    - The therapists were not blinded to the group assignment, given the nature of the interventions.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


## Item 7

### Details of evaluation

- Aim of evaluation: Determine whether the assessors are unaware of the treatment group assignment for each subject.
- Criterion for satisfaction: 
    1. The study must explicitly state in the methods that assessors were unaware of which group subjects were allocated to. In cases where key outcomes are self-reported, the subject is the assessor, and they must be blinded. This blinding of assessors, whether they are subjects providing self-reports or external raters, must be clearly described in the methodology.
- Considerations for evaluation:
    - Methods for Blinding: Techniques such as the use of sealed opaque envelopes, central telephone systems, or web-based systems are common methods to ensure blinding. For trials involving complex interventions where blinding might be challenging (like exercise programs or surgeries), the methodology needs to be clearly articulated to see if blinding was feasible.
    - Complex Interventions: In trials with interventions that cannot be blinded, such as some surgical procedures or physical therapies, the reports must articulate how they managed potential biases.
    - Reporting: Information about blinding is typically detailed in the methods section and can be crucial for understanding how bias was managed in the study.
    - Challenges with Terminology: Terms like "single-blind," "double-blind," or "triple-blind" are often used ambiguously, so detailed descriptions of who was blinded and how are essential for proper evaluation.

### Steps for Evaluation

1. **Identify Blinding Statement**: Look for a statement in the study that explicitly indicates whether the assessors were unaware of the treatment group assignments.
2. **Evaluate Self-Reported Outcomes**: If key outcomes are self-reported, ensure the study clearly states that subjects (as assessors) were blinded to their group assignments.
3. **Document Findings**: Record whether the blinding of assessors or subjects is explicitly mentioned and described.

### Examples:
- satisfied:
    - all of the out-come measures were administered to the patients by the same blinded assessor.
- not satisfied: 
    - This was a randomized controlled trial with no assessor blinding.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


## Item 8


### Details of evaluation

- Aim of evaluation: Determine whether this research has adequate follow-up data points.
- Criterion for satisfaction: 
    1. Subject Reporting: The report must explicitly state:
        - The number of subjects initially allocated to groups.
        - The number of subjects from whom key outcome measures were obtained.
    2. Follow-Up Completeness:
        - The overall follow-up completeness is considered satisfactory if measures of at least one key outcome were obtained from more than 85% of the total subjects initially allocated to all groups combined.
        - This means the total loss rate should be less than 15%.
        - If the initial number of participants included and the numbers of participants who completed the study are not well documented, this criterion is not satisfied.

### Steps for evaluation

1. **List Initial Allocation**: Record the number of subjects initially allocated to each group. If not explicitly stated in the article, note it as "not available." 
2. **List Final Completion**: Record the number of subjects in each group who completed the study and whose data could be analyzed. If there are multiple follow-up points, list the number of subjects for each time point. If not explicitly stated in the article, note it as "not available." 
3. **Calculate Total Follow-Up Rate**: Calculate the total follow-up rate for all groups combined at each time point using the formula: 
    -  $$\text{Total Follow-Up Rate} = \frac{\text{Total Number of Subjects Analyzed}}{\text{Total Number of Subjects Initially Allocated}}$$ 
    - Perform this calculation for each time point if multiple follow-up points are provided. 
4. **Determine Satisfaction**: 
    - If the initial allocation numbers and the completion numbers at each time point are not explicitly stated, mark as "not satisfied." 
    - If the total follow-up rate is 85% or higher, mark as "satisfied."



### Examples:
- satisfied:
    - The study randomly assigned 48 individuals to 3 groups, with 16 people per group. All 16 participants in each group completed the study and their data were analyzed, resulting in a 100% retention rate for each group.
- not satisfied: 
    - The number of subjects initially allocated to groups and the number of subjects from whom key outcome measures were obtained were not both reported.
    - The follow-up rate for at least one group is less than 85%. For example, if the number of subjects from whom key outcome measures were obtained divided by the number of subjects initially allocated to the group is less than 0.85.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```

## Item 9


### Details of evaluation

- Aim of evaluation: Determine whether the study uses an Intention to Treat (ITT) analysis to maintain the integrity of random allocation and minimize bias.
- Definition of Intention to Treat Analysis:
    - Intention to treat (ITT) analysis involves analyzing data as if all subjects received the treatment or control condition they were initially allocated, regardless of what actually occurred during the trial. This approach accounts for protocol deviations and maintains the random allocation balance, thereby minimizing bias.
- Criterion for satisfaction: 
    1. The criterion is met if the study explicitly states that an ITT analysis was used. Alternatively, the study can fulfill this requirement if it reports that all subjects received the treatment or control conditions as initially allocated, or that subjects were analyzed according to their initial group allocation.

### Steps for Evaluation

1. **Identify ITT Statement**: Look for a statement in the study that explicitly indicates whether an ITT analysis was used.
2. **Evaluate Allocation Reporting**: Check if the study reports that all subjects received the treatment or control conditions as initially allocated or were analyzed according to their initial group allocation.
3. **Document Findings**: Record whether the use of ITT analysis or equivalent reporting is explicitly mentioned and described.

### Examples:
- satisfied:
    - An intention-to-treat analysis was performed.
- not satisfied: 
    - The analysis was conducted using a per-protocol approach, where only participants who completed the study according to the specified treatment protocol were included in the final evaluation. As a result, individuals who dropped out or did not adhere to the assigned treatment were excluded from the analysis.

### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```

## Item 10

### Details of evaluation

- Aim of evaluation: Determine whether the study provides results of statistical comparisons between groups for key outcomes.
- Criterion for satisfaction: 
    1. The study must report results of between-group statistical comparisons for at least one key outcome. This can include comparisons of outcomes measured after treatment administration or comparisons of changes over time between groups. The comparisons may involve hypothesis testing (e.g., providing a p-value) or providing estimates (e.g., mean or median differences, differences in proportions, number needed to treat, relative risk, or hazard ratio) along with their confidence intervals.

### Steps for Evaluation

1. **Identify Key Outcomes**: Determine which outcomes the study identifies as key.
2. **Check for Between-Group Comparisons**: Look for reported results of between-group statistical comparisons for these key outcomes. Ensure that the comparisons include:
    - Comparisons of outcomes measured after treatment administration or
    - Comparisons of changes over time between groups (e.g., group × time interaction).
3. **Evaluate the Form of Comparison**: Confirm that the comparisons are presented as either:
    - Hypothesis testing with a p-value, or
    - Estimates with confidence intervals (e.g., mean/median differences, differences in proportions, number needed to treat, relative risk, hazard ratio).
4. **Document Findings**: Record whether the study reports between-group statistical comparisons for key outcomes and provide details of these comparisons, including the form of the comparison (p-values or estimates with confidence intervals).

### Examples:
- satisfied:
    - Between- group analyses revealed significant differences and large effects among the three groups...
- not satisfied: 
    - The study only present the differences between different time points within group, but not showed any comparisons between group.

### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```


## Item 11


### Details of evaluation

- Aim of evaluation:  Determine whether the study reports point measures and measures of variability for at least one key outcome.
- Definitions
    - Point Measure: A measure of the size of the treatment effect, described as a difference in group outcomes or as the outcome in each group.
    - Measures of Variability: Statistical measures that describe the variability of the data, including:
        - Standard Deviations (SDs)
        - Standard Errors (SEs)
        - Confidence Intervals (CIs)
        - Interquartile Ranges (IQRs)
        - Ranges
- Criterion for Satisfaction
    1. The study must report point measures of the treatment effect, which can be described as a difference in group outcomes or as the outcome in each group.
    2. The study must include measures of variability, such as SDs, SEs, CIs, IQRs, or ranges.
    3. Point measures and/or measures of variability may be provided graphically (e.g., error bars in a figure) as long as it is clear what is being graphed and what the error bars represent (e.g., SDs or SEs).
    4. For categorical outcomes, this criterion is satisfied if the number of subjects in each category is given for each group.

### Steps for evaluation

1. **Identify Point Measures on key outcome**: Look for descriptions of the treatment effect size, which can be given as differences in group outcomes or outcomes for each group.
2. **Check for Measures of Variability on key outcome**: Verify that the study includes measures of variability such as SDs, SEs, CIs, IQRs, or ranges. These can be provided numerically or graphically.
3. **Evaluate Graphical Representations on key outcome**: If measures of variability are provided graphically (e.g., as error bars), ensure that it is clear what is being graphed and what the error bars represent.
4. **Check Categorical Outcomes**: For studies with categorical outcomes, confirm that the number of subjects in each category is provided for each group.
5. **Document Findings**: Record whether the study reports point measures and measures of variability for the treatment effect and provide details on how these are presented.

### Examples:
- satisfied:
    - The study present mean (SD)  for each group on key outcome measure.
- not satisfied: 
    - The study present mean (SD)  for each group on participants' demographic variables but not on key outcome measure.

### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {related texts from the research that support your decision}
```

# Follow-up inqueries

## item 6

1. Blinding Information Presence
    - Question: Does the research documentation explicitly mention whether the therapists were blinded to the treatment group assignments?
        - Yes/No: ____
2. Blinding Description Evaluation
    - Question: If blinding is mentioned, does the documentation provide a clear description indicating that therapists were unaware of whether subjects received the treatment or a control?
        - Yes/No: ____
        - Follow-Up: If yes, please specify the description provided in the research documentation: ____
3. Document Findings
    - Question: Based on your review, is the blinding of therapists explicitly mentioned and adequately described to meet the criterion for satisfaction?
        - Yes/No: ____
        - Comments: Please provide any additional comments or observations regarding the blinding of therapists: ____

## item 7

1. Identify Blinding Statement
    - Question: Does the research documentation explicitly state that the assessors were unaware of the treatment group assignments?
        - Yes/No: ____
2. Evaluate Self-Reported Outcomes
    - Question: If key outcomes are self-reported, does the study clearly state that subjects (as assessors) were blinded to their group assignments?
        - Yes/No/Not Applicable: ____
        - Follow-Up: If yes, please specify the description provided in the research documentation: ____
3. Document Findings
    - Question: Based on your review, is the blinding of assessors (or subjects in the case of self-reported outcomes) explicitly mentioned and adequately described to meet the criterion for satisfaction?
        - Yes/No: ____
        - Comments: Please provide any additional comments or observations regarding the blinding of assessors: ____

## item 8

1. List initial allocation
    - Question: does the research documentation explicitly state the number of subjects initially allocated to each group?
        - yes/no: ____
        - follow-up: if yes, please provide the numbers for each group: ____
2. List final completion
    - Question: does the research documentation explicitly state the number of subjects in each group who completed the study and whose data could be analyzed?
        - yes/no: ____
        - follow-up: if yes, please provide the numbers for each group and for each follow-up time point if applicable: ____
3. Calculate Total Follow-Up Rate
    - Question: based on the provided numbers, what is the follow-up rate in total at each time point? The total follow-up rate based on the total number of subjects initially allocated and those who completed the study across all groups.
        - total follow-up rate: ____
4. Determine satisfaction
    - Question: based on your calculations and the documentation provided, does the study meet the criterion for having adequate follow-up data points (i.e., follow-up rate of 85% or higher for each group)?
        - yes/no: ____
        - comments: please provide any additional comments or observations regarding the follow-up data points: ____

## item 9

1. Identify ITT statement
    - Question: does the research documentation explicitly state that an intention to treat (itt) analysis was used?
        - Yes/no: ____
2. Evaluate allocation reporting
    - Question: does the study report that all subjects received the treatment or control conditions as initially allocated, or were analyzed according to their initial group allocation?
        - Yes/no: ____
        - Follow-up: if yes, please specify the description provided in the research documentation: ____
3. Document findings
    - Question: based on your review, is the use of itt analysis or equivalent reporting explicitly mentioned and adequately described to meet the criterion for satisfaction?
        - Yes/no: ____
        - Comments: please provide any additional comments or observations regarding the use of itt analysis: ____

## item 10

- Identify key outcomes
    - Question: does the research documentation identify key outcomes for the study?
        - Yes/no: ____
        - Follow-up: if yes, please list the key outcomes identified in the research documentation: ____
1. Check for between-group comparisons
    - Question: does the study report results of between-group statistical comparisons for the key outcomes?
        - Yes/no: ____
        - Follow-up: if yes, do the comparisons include:
            - Comparisons of outcomes measured after treatment administration? Yes/no: ____
            - Comparisons of changes over time between groups (e.g., group × time interaction)? Yes/no: ____
2. Evaluate the form of comparison
    - Question: are the between-group comparisons presented as either:
        - Hypothesis testing with a p-value? Yes/no: ____
        - Estimates with confidence intervals (e.g., mean/median differences, differences in proportions, number needed to treat, relative risk, hazard ratio)? Yes/no: ____
3. Document findings
    - Question: based on your review, does the study report between-group statistical comparisons for key outcomes and are they presented in an acceptable form?
        - Yes/no: ____
        - Comments: please provide any additional comments or observations regarding the between-group statistical comparisons for key outcomes: ____

## item 11

1. Identify point measures on key outcome
    - Question: does the study report point measures of the treatment effect, either as differences in group outcomes or as outcomes for each group?
        - Yes/no: ____
        - Follow-up: if yes, please provide the point measures described in the research documentation: ____
2. Check for measures of variability on key outcome
    - Question: does the study include measures of variability such as standard deviations (sds), standard errors (ses), confidence intervals (cis), interquartile ranges (iqrs), or ranges?
        - Yes/no: ____
        - Follow-up: if yes, please specify the measures of variability provided in the research documentation: ____
3. Evaluate graphical representations on key outcome
    - Question: if measures of variability are provided graphically (e.g., as error bars), is it clear what is being graphed and what the error bars represent (e.g., sds or ses)?
        - Yes/no/not applicable: ____
        - Follow-up: if yes, please describe the graphical representation and what the error bars represent: ____
4. Check categorical outcomes
    - Question: for studies with categorical outcomes, does the study report the number of subjects in each category for each group?
        - Yes/no/not applicable: ____
        - Follow-up: if yes, please provide the numbers reported for each category and group: ____
5. Document findings
    - Question: based on your review, does the study report point measures and measures of variability for the treatment effect and are they presented clearly?
        - Yes/no: ____
        - Comments: please provide any additional comments or observations regarding the reporting of point measures and measures of variability: ____