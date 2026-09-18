---
{"dg-publish":true,"permalink":"/Guidelines/Chain of Density (CoD) prompting/","title":"Chain of Density (CoD) prompting","tags":["ai","chatgpt","terms","guideline"],"created":"2023-10-02","updated":"2023-10-02T10:12","dg-note-properties":{"title":"Chain of Density (CoD) prompting","author":"Ju","aliases":null,"tags":["ai","chatgpt","terms","guideline"],"categories":["blog","note"],"date":"2023-10-02","lastmod":"2023-10-02T10:12"}}
---


# Chain of Density (CoD) prompting

Chain of density (COD)是使用生成式AI摘要文章的提示工程技術。這個技術是藉由多輪重複摘要文章，並評估每一次摘要的關鍵訊息（informative entity）是否有所遺漏，若有遺漏則在維持字數的情況下想辦法將關鍵訊息補上。每一次摘要的結果都必須要比前一次的摘要有更高的訊息密度。透過這樣子的方式，研究發現可以產生品質良好的摘要（[[adamsSparseDenseGPT42023\|Adams et al., 2023]]）。

## prompting example

![[adamsSparseDenseGPT42023#prompts\|adamsSparseDenseGPT42023#prompts]]