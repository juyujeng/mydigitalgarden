---
{"dg-publish":true,"permalink":"/Projects/PEDro/single item prompt item 8/","title":"single item prompt","tags":["prompt","ai","chatgpt"],"created":"2024-07-26T16:36","updated":"2024-07-28T00:43"}
---


# Item 6

# Item 7

# Item 8: adequate follow up

## Basic prompt

### General instruction
You are a professional scientific researcher. Your task is to evaluate the quality of the medical research provided to you. Follow the detailed instructions below carefully. If you do it right, I'll tip you $1000.

### Details of evaluation

- Aim of evaluation: Determine whether this research has adequate follow-up data points.
- Criterion for satisfaction: 
    1. The report must **explicitly state both** the number of subjects initially allocated to groups and the number of subjects from whom key outcome measures were obtained.
    2. If measures of at least one key outcome were obtained from more than 85% of the subjects initially allocated to groups, then this criterion is satisfied. This means the loss rate for each group should be less than 15%. If the initial numbers of participants for each group and the numbers of participants who completed the study are not well documented, this criterion is not satisfied.
- Examples:
    - satisfied:
        - The study randomly assigned 48 individuals to 3 groups, with 16 people per group. All 16 participants in each group completed the study and their data were analyzed, resulting in a 100% retention rate for each group.
    - not satisfied: 
        - The number of subjects initially allocated to groups and the number of subjects from whom key outcome measures were obtained were not both reported.
        - The follow-up rate for at least one group is less than 85%. For example, if the number of subjects from whom key outcome measures were obtained divided by the number of subjects initially allocated to the group is less than 0.85.


### Export the results

export the result with the following format

```
satisfied or not: Y/N
evidence: {evidence from the research that support your decision}
```


## chain of thought

### General instruction
You are a professional scientific researcher. Your task is to evaluate the quality of the medical research provided to you. Follow the detailed instructions below carefully. If you do it right, I'll tip you $1000.

### Details of evaluation

- Aim of evaluation: Determine whether this research has adequate follow-up data points.
- Criterion for satisfaction: 
    1. The report must **explicitly state both** the number of subjects initially allocated to groups and the number of subjects from whom key outcome measures were obtained.
    2. If measures of at least one key outcome were obtained from more than 85% of the subjects initially allocated to groups, then this criterion is satisfied. This means the loss rate for each group should be less than 15%. If the initial numbers of participants for each group and the numbers of participants who completed the study are not well documented, this criterion is not satisfied.

### Steps for evaluation

- **List Initial Allocation**: Record the number of subjects initially allocated to each group. If not explicitly stated in the article, note it as "not available."
- **List Final Completion**: Record the number of subjects in each group who completed the study and whose data could be analyzed. If there are multiple follow-up points, list the number of subjects for each time point. If not explicitly stated in the article, note it as "not available."
- **Calculate Follow-Up Rate**: Calculate the follow-up rate for each group at each time point using the formula: 
    - $$\text{Follow-Up Rate} = \frac{\text{Number of Subjects Analyzed}}{\text{Number of Subjects Initially Allocated}}$$
    - Perform this calculation for each time point if multiple follow-up points are provided.
- **Determine Satisfaction**:
    - If the initial allocation numbers and the completion numbers at each time point are not explicitly stated, mark as "not satisfied."
    - If for any time point, the follow-up rate for each group is 85% or higher, mark as "satisfied."


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
evidence: {evidence from the research that support your decision}
```


# Item 9

# Item 10

# Item 11