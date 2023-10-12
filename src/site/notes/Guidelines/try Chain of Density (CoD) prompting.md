---
{"dg-publish":true,"permalink":"/Guidelines/try Chain of Density (CoD) prompting/","title":"試用 Chain of Density (CoD) prompting","tags":["blog","chatgpt","ai"],"created":"2023-10-12","updated":"2023-10-12"}
---


本文紀錄使用 [[Guidelines/Chain of Density (CoD) prompting\|Chain of Density (CoD) prompting]] 摘要文章重點的使用心得，並比較用CoD prompting以及簡單地一句「請以200字摘要以下文章」所得到的結果。

> [!FAQ]- Chain of Density (CoD) prompting (點開觀看)
> Article: {文章內容…} 
> You will generate increasingly concise, entity-dense summaries of the above article in traditional Chinese. Repeat the following 2 steps 5 times. 
> Step 1. Identify 1-3 informative entities (";" delimited) from the article which are missing from the previously generated summary. 
> Step 2. Write a new, denser summary of identical length which covers every entity and detail from the previous summary plus the missing entities. 
> A missing entity is: 
> - relevant to the main story, 
> - specific yet concise (5 words or fewer), 
> - novel (not in the previous summary), 
> - faithful (present in the article), 
> - anywhere (can be located anywhere in the article). 
> 
> Guidelines: 
> - The first summary should be long (4-5 sentences, ~80 words) yet highly non-specific, containing little information beyond the entities marked as missing. Use overly verbose language and fillers (e.g., "this article discusses") to reach ~80 words. 
> - Make every word count: rewrite the previous summary to improve flow and make space for additional entities. 
> - Make space with fusion, compression, and removal of uninformative phrases like "the article discusses". 
> - The summaries should become highly dense and concise yet self-contained, i.e., easily understood without the article. 
> - Missing entities can appear anywhere in the new summary. 
> - Never drop entities from the previous summary. If space cannot be made, add fewer new entities. 
> 
> Remember, use the exact same number of words for each summary. 
> Answer in JSON. The JSON should be a list (length 5) of dictionaries whose keys are "Missing_Entities" and "Denser_Summary". the content should be in traditional Chinese

這裡使用兩篇中文文章進行分析，分別是[今夏登革熱來勢洶洶，該怎麼防治？有疫苗嗎？](https://pansci.asia/archives/369781)以及[哈瑪斯突襲以色列，全局一次看：兩種美國中東戰略途徑](https://voicettank.org/%E5%93%88%E7%91%AA%E6%96%AF%E7%AA%81%E8%A5%B2%E4%BB%A5%E8%89%B2%E5%88%97%E5%85%A8%E5%B1%80%E4%B8%80%E6%AC%A1%E7%9C%8B%E5%85%A9%E7%A8%AE%E7%BE%8E%E5%9C%8B%E4%B8%AD%E6%9D%B1%E6%88%B0/)。這兩篇文章的字數都超過兩千字，且都有一定的專業性，若有好的摘要可以幫助文章理解。

根據兩篇文章摘要的結果，CoD prompting每一輪的確可以產生比上一輪更好的摘要結果，但最後的摘要文章可能流暢度不佳，反而使用簡單的prompt就可以得到還算滿意的結果。不知道是文章類型還是文章語言的限制，需要進一步的探索。另外，當文章的長度較長時，使用CoD prompting容易發生錯誤（還是我的運氣不好？），得要重複幾次才能順利得到最後的成果。

## [登革熱](https://pansci.asia/archives/369781)文章摘要分析

在登革熱文章的摘要中，使用simple prompt的結果雖然超過字數限制，但是看起來比較像是一篇完整的短文。使用CoD prompting給出的摘要，的確每一輪產生的訊息量較豐富，但是卻失去了句子之間的連接性，最後得到許多訊息的組合，但非流暢的段落。

### CoD prompting 結果

#### 第1輪
> [!NOTE] "Missing_Entities": "登革熱疫苗; TAK-003; Dengvaxia"
> 本文討論了台灣登革熱病例的增加及其影響。文章中提及登革熱疫苗的開發，特別是提到了 TAK-003 和 Dengvaxia 兩種疫苗。TAK-003 為日本武田製藥所研發，已通過一些國家的審批，而 Dengvaxia 則僅能施打於已感染過登革熱的個體。此外，為預防登革熱的擴散，政府和民眾需採取一些必要的防蚊措施，以減少病例的進一步增加。

#### 第2輪
> [!NOTE] "Missing_Entities": "蚊子生殖營養週期; 80.2%的不感染保護力; 1970 年代"
> 台灣登革熱病例升高引起關注。文章探討疫苗如 TAK-003 和 Dengvaxia 的應用。TAK-003 在多國獲准，可提供80.2%的不感染保護力。登革熱疫苗自1970年代研發，面對眾多挑戰。文章還提到蚊子的生殖營養週期，及清除積水容器以控制蚊子數量，作為防範登革熱的重要措施，旨在減少病例進一步增加，並期盼新疫苗能對抗登革熱。

#### 第3輪
> [!NOTE] "Missing_Entities": "4,338 例本土病例; ADE效應; 90.4％的重症保護力"
> 台灣登革熱病例增至4,338例。TAK-003 和 Dengvaxia 疫苗助防控，前者在多國獲准，提供80.2%不感染及90.4％重症保護力。疫苗研發自1970年代，面對ADE效應挑戰。文章強調蚊子生殖營養週期理解及清除積水容器的重要性，以控制病媒蚊數量，降低登革熱傳播風險。民眾期待新疫苗能提供更好的保護，以對抗日益嚴重的登革熱疫情。

#### 第4輪
> [!NOTE] "Missing_Entities": "歐盟、英國、巴西、印尼、泰國、阿根廷; ADE效應; 61.2%的不感染保護力"
> 台灣登革熱病例增至4,338例。TAK-003疫苗在歐盟、英國、巴西、印尼、泰國、阿根廷獲准，提供80.2%不感染、90.4％重症及61.2%長期保護。Dengvaxia僅適用於曾感染者。疫苗研發自1970年代，ADE效應是主要挑戰。文章強調理解蚊子生殖營養週期和清除積水容器以控制病媒蚊數量，降低登革熱風險。民眾期待新疫苗能提供更強效的登革熱保護。

#### 第5輪
> [!NOTE] "Missing_Entities": "日本武田製藥; 25-100隻新出生的雌蚊; 4年半的持續追蹤"
> 台灣登革熱病例達4,338例。日本武田製藥的TAK-003疫苗在多國獲准，提供80.2%不感染、90.4％重症及61.2%的4年半保護。Dengvaxia僅適用於曾感染者。自1970年代起疫苗研發面臨ADE效應挑戰。文章揭示蚊子生殖營養週期，一隻雌蚊可產生25-100隻新出生的雌蚊，強調清除積水容器以控制病媒蚊數量，降低登革熱風險。民眾期盼新疫苗能更有效對抗登革熱。

### Simple prompt結果


> [!NOTE] Simple prompt
> 文章分析了台灣近期登革熱疫情的嚴重性和原因。指出傳統上9月是登革熱的高峰期，但台灣本土缺乏登革熱病毒株，疫情通常由境外移入患者帶入。近年來由於COVID-19封鎖和境外移入病例的減少，登革熱疫情得到控制。但隨著交通恢復，2023年已有158例境外移入病例。台灣與東南亞的交流增多，使得登革熱疫情與東南亞的疫情嚴重性高度相關。文章也強調防蚊措施，如清除積水容器以減少蚊子繁殖。在登革熱疫苗方面，雖然開發困難，但有新的疫苗，如日本的TAK-003，展示了一定的效果和保護力，並且不會產生ADE效應，即使在未曾感染過登革熱的人群中也能安全施打。這些新疫苗為未來登革熱的預防提供了希望。

## [哈瑪斯突襲以色列](https://voicettank.org/%E5%93%88%E7%91%AA%E6%96%AF%E7%AA%81%E8%A5%B2%E4%BB%A5%E8%89%B2%E5%88%97%E5%85%A8%E5%B1%80%E4%B8%80%E6%AC%A1%E7%9C%8B%E5%85%A9%E7%A8%AE%E7%BE%8E%E5%9C%8B%E4%B8%AD%E6%9D%B1%E6%88%B0/)文章摘要分析

類似登革熱文章分析的結果，使用simple prompt得到的結果比較像是一篇完整通順的文章。使用CoD prompting在這一篇文章中只得到為了塞進關鍵字而多次使用「提及…」，造成有許多的關鍵字但句子不完整的情況。

### CoD prompting 結果

#### 第0輪

> [!NOTE] 
> 這篇文章討論了美國的外交手段和策略。文章強調，要真正理解美國的外交策略，我們必須考慮其內政和文化背景，特別是「個人主義」這一核心概念。美國的個人主義與其在國際舞台上的行為有著密切的關聯。此外，文章還提到了與以色列和哈瑪斯之間的緊張關係，以及美國的回應和行動。


#### 第1輪

> [!NOTE] Missing entities: 美援, 地中海東部, 哈瑪斯盟國
> 這篇文章討論了美國的外交手段和策略，並提及孤立主義，並提及美國航母，並提及拜登告訴納坦雅虎，並提及美援，並提及地中海東部，並提及哈瑪斯盟國。文章強調，要真正理解美國的外交策略，我們必須考慮其內政和文化背景，特別是「個人主義」這一核心概念。美國的個人主義與其在國際舞台上的行為有著密切的關聯。此外，文章還提到了與以色列和哈瑪斯之間的緊張關係，以及美國的回應和行動。


#### 第2輪

> [!NOTE] Missing entities: F35, F15, 加薩走廊
> 這篇文章討論了美國的外交手段和策略，並提及孤立主義，並提及美國航母，並提及拜登告訴納坦雅虎，並提及美援，並提及地中海東部，並提及哈瑪斯盟國，並提及F35，並提及F15，並提及加薩走廊。文章強調，要真正理解美國的外交策略，我們必須考慮其內政和文化背景，特別是「個人主義」這一核心概念。美國的個人主義與其在國際舞台上的行為有著密切的關聯。此外，文章還提到了與以色列和哈瑪斯之間的緊張關係，以及美國的回應和行動。


#### 第3輪

> [!NOTE] Missing entities: 政府深陷, 議員蓋茲
> 這篇文章討論了美國的外交手段和策略，並提及孤立主義，並提及美國航母，並提及拜登告訴納坦雅虎，並提及美援，並提及地中海東部，並提及哈瑪斯盟國，並提及F35，並提及F15，並提及加薩走廊，並提及政府深陷，並提及議員蓋茲。文章強調，要真正理解美國的外交策略，我們必須考慮其內政和文化背景，特別是「個人主義」這一核心概念。美國的個人主義與其在國際舞台上的行為有著密切的關聯。此外，文章還提到了與以色列和哈瑪斯之間的緊張關係，以及美國的回應和行動。

#### 第4輪

> [!NOTE] Missing entities: No new entities
> 這篇文章討論了美國的外交手段和策略，並提及孤立主義，並提及美國航母，並提及拜登告訴納坦雅虎，並提及美援，並提及地中海東部，並提及哈瑪斯盟國，並提及F35，並提及F15，並提及加薩走廊，並提及政府深陷，並提及議員蓋茲。文章強調，要真正理解美國的外交策略，我們必須考慮其內政和文化背景，特別是「個人主義」這一核心概念。美國的個人主義與其在國際舞台上的行為有著密切的關聯。此外，文章還提到了與以色列和哈瑪斯之間的緊張關係，以及美國的回應和行動。


### Simple prompt結果


> [!NOTE] 
> 本文主要討論美國外交政策與中東局勢的緊密關聯。文章提到，若不理解美國文化中的「個人主義」如何影響其內外政策，就可能誤判美國的外交動向。近期以色列與哈瑪斯的緊張關係升級，哈瑪斯對以色列發動攻擊，引起美國航母駛向地中海東部進行嚇阻。同時，美國內部的政治局勢也呈現動盪，特別是拜登與川普兩派對於中東政策的不同看法。
> 文章中還描述了以色列和哈瑪斯之間的矛盾，以及哈瑪斯在加薩走廊的崛起。哈瑪斯這次的攻擊，突顯了其對抗以色列的能力，這也對以色列的政治局勢造成衝擊，特別是首相納坦雅虎面臨的壓力。
> 文章最後指出，美國在中東的投入可能會影響其對其他地區，如烏克蘭和台灣的戰略資源分配。因此，台灣應保持警惕，確保自己的戰備。
> 總結，美國的外交政策，尤其在中東，既受到內部政治局勢的影響，也會影響其全球策略佈局。


## 其他紀錄

本來我嘗試使用chat with Bing功能，試圖讓ChatGPT讀取文章連結的內容，但使用CoD prompting卻無法正確地產生的摘要，並顯示無法完整讀取文章內容的錯誤訊息。

另外，若刪除`Answer in JSON. The JSON should be a list (length 5) of dictionaries whose keys are "Missing_Entities" and "Denser_Summary".`，ChatGPT會產生一連串內容重複的回應，可能是將每一輪的結果都沒有區隔地印出來，不容易閱讀。