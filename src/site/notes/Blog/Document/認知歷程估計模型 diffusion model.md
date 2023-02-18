---
{"dg-publish":true,"permalink":"/Blog/Document/認知歷程估計模型 diffusion model/","title":"認知歷程估計模型 diffusion model","tags":["blog","psychology","method","guideline"]}
---


# diffusion model: 認知歷程估計模型

反應時間是認知作業常用的指標，我們很常使用平均反應時間的差異來指涉不同的認知歷程的差異。例如在常見的叫色測驗（Stroop task）當中會使用一致嘗試（congruent trial）以及不一致嘗試（incongruent trial）的平均反應時間的差異大小來作為認知抑制功能的高低。

不過這樣子的做法對於反應時間只使用到它的平均數，其他與反應時間有關的訊息都被忽略了（例如反應時間的分佈情況、變異程度）。Ratcliff（1978）提出了diffusion model，可以完整的使用反應時間的分佈相關的資訊。藉由這個模型可以估計出幾個不同的參數，而且每一個參數都代表著一種認知歷程，因此在理論的驗證上可以做出更精準的假設以及驗證。

## The Basic Diffusion Model

[圖](obsidian://open?vault=Ju%20note&file=review%20works%2Fdiffusion%20model%2Fimage-20211203144707515.png)

基本的diffusion model會估計四個參數，分別代表四個不同的認知歷程

- $\nu$: **drift rate**, the speed of information uptake
  - 訊息處理能力，受到個體的認知能力以及作業難度的影響。如果是比個體間的差異，兩麼就是前者，而若是比較作業間的差異就是後者

- $a$: **threshold seperation**, the amount of information that is considered for a decision
  - 較保守的決策風格，會有比較大的$a$
  - 對於speed versus accuracy的指導語很敏感

- $z$: **starting point**, bias to behave toward one kind of response. usually reported as $z_r = z/a$. if $z_r$ is not $\frac{1}{2}a$, it is biased.
  - 這個會受到許多因素的影響，例如說reward。如果回答某一個反應的reward明顯地比較高，會偏向那一個回答。

- $t_0$ or $t_{err}$: duration of nondecisional processes
  - Such processes may comprise basic *encoding processes*, the configuration of working memory for a task, and processes of *response execution* (i.e., motor activity).
  - 通常會假設$t_0$在兩種反應是一樣的。然而實際上也有可能是不同的，可以將這個參數定為要隨著刺激不同而不同的要估計的參數。

但要使用這個模型在實驗派典的使用以及作業要測量的認知歷程都有限制以及假設，下面簡單介紹。

## diffusion model基本假設

- **Binary Decisions**: Diffusion Model用來描述binary choice decision process，也就是要做A反應或是B反應。它假設決策的歷程可以用Wiener diffusion process來描述相關訊息累進的過程。當訊息累積到一定程度（超過閾值）便會做出決策反應。

- **Continuous Sampling**: decisions are based on a continuous sampling process
	- many simple decision tasks information sampling can be conceived as a continuous process.
- **Single-Stage Decisions**: 一開始的發展是假設決策的歷程只有一步。如果是兩階段以上的決策歷程並不適用。
	- 然而現在已有研究者提出多階段歷程的模型
	- belief bias task應該就要考量多階段的（有的時候會多想）
- **Constancy of Parameter Values Over Time**:
	- 通常會假設模型參數是常數（現已有提出隨機變數的模型），不會隨著時間而改變。所以不會作業一開始是某個值，作業快要完成時卻變成另一個值。
- **Decision Times**:
	- 通常用在latency < 1 second
	- 如果決策時間很長（例如大於10秒），很有可能違反上述的假設。 
- **Numbers of Trials and Percentage of Errors**：
	- trials數量要夠多（沒有一個絕對值，隨著估計的方法以及參數的數量而變）
	- 錯誤數（或者說另一種反應的反應數）要夠多，才有辦法估出兩個歷程。


## 心得

雖然diffusion model看來好像很厲害，但在認知心理學領域當中使用尚未普遍。可能是受限於過去電腦運算的能力不佳而發展較慢，也可能是適用的作業需要驗證才能夠確定是否能符合其假設。若要將這個模型應用到評估工具可能還需要更多更完整的發展以及驗證。但現在似乎開始有人嘗試進行相關的研究工作了。

這些被估計出來的參數所能夠反應的認知歷程實際上到底是什麼，也是研究者在使用上需要仔細討論的。在使用上可能更需要理論基礎。