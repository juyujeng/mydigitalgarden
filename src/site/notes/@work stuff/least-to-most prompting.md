---
{"dg-publish":true,"permalink":"/@work stuff/least-to-most prompting/","title":"Least-to-most prompting","tags":["ai","chatgpt","prompt"],"created":"2024-01-15T14:42","updated":"2024-01-15T15:12"}
---


[[@work stuff/least-to-most prompting\|Least-to-most prompting]] 籍由將大任務分細子任務，讓大型語言模型可以處理較複雜的大任務。使用[[@work stuff/least-to-most prompting\|Least-to-most prompting]] 包含兩個階段：


> 1. Decomposition. 
>     - The prompt in this stage contains constant examples that demonstrate the decomposition, followed by the specific question to be decomposed.
> 2. Subproblem solving. 
>     - The prompt in this stage consists of three parts: 
>         - (1) constant examples demonstrating how subproblems are solved; 
>         - (2) a potentially empty list of previously answered subquestions and generated solutions, and 
>         - (3) the question to be answered next.


## example

> 有一個小山坡，小明爬上去需要花4分鐘，爬下來需要花1分鐘。15分鐘內，小明可以爬上再爬下來回幾次？

1. Decomposition
    - > "有一個小山坡，小明爬上去需要花4分鐘，爬下來需要花1分鐘。15分鐘內，小明可以爬上再爬下來回幾次？" 該怎麼解決這個問題？
2. Subproblem solving
    - 包含子問題
        - > "有一個小山坡，小明爬上去需要花4分鐘，爬下來需要花1分鐘。15分鐘內，小明可以爬上再爬下來回幾次？" Q: 爬上爬下一趙花多少時間？
    - 將子問題的答案附上，再進一步提問
        - > "有一個小山坡，小明爬上去需要花4分鐘，爬下來需要花1分鐘。15分鐘內，小明可以爬上再爬下來回幾次？" Q: 爬上爬下一趙花多少時間？ A : 爬上爬下一趟要花5分鐘 Q: 那麼15分鐘內可以爬上爬下來回幾次？
## References

Zhou, D., Schärli, N., Hou, L., Wei, J., Scales, N., Wang, X., ... & Chi, E. (2022). Least-to-most prompting enables complex reasoning in large language models. _arXiv preprint arXiv:2205.10625_.