---
{"dg-publish":true,"permalink":"/Hsu method/","title":"Hsu's multiple comparison for the best method","tags":["terms","statistics","posthoc","multiple_comparison"],"created":"2024-01-08","updated":"2024-01-08T14:32"}
---


- 由 Hsu (1996) 發展的多重比較法，是由Dunnett法修改而來。 Dunnett 法在比較時先設定一組為控制組，其他組的平均都跟這個控制組比。而 Hsu 的方法則是以表現最佳的組為基準，其他的組都跟這個表現最佳的組別比較，故被稱為 Hsu's multiple comparison with best method (Hsu's MCB)。
- 如果控制組就是表現最佳的組，那麼Hsu's MCB和Dunnett結果是一樣的

## R

- 使用`linfct`設定 linear contrast matrix

```
dht <- glht(aov.model, linfct = mcp( site = "Dunnett" ), + alternative = "two.sided")
summary(dht)
```