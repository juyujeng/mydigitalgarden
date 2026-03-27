---
{"dg-publish":true,"permalink":"/Blog/Life/ChatGPT可以幫我改code/","title":"ChatGPT可以幫我改code，但是我得先發現問題出在哪裡","tags":["blog","ai","webpage","coding"],"created":"2023-02-24","updated":"2023-02-25T10:57","dg-note-properties":{"title":"ChatGPT可以幫我改code，但是我得先發現問題出在哪裡","author":"Ju","tags":["blog","ai","webpage","coding"],"categories":["blog","life"],"date":"2023-02-24","summary":null,"lastmod":"2023-02-25T10:57"}}
---




obsidian有很好用的CSS片段叫做[Modular CSS Layout for Obsidian](https://github.com/efemkay/obsidian-modular-css-layout)，它可以很方便地將筆記段落排版為多欄位的形式。在我的電腦上使用起來完全沒有問題，但是當我把筆記放到[網頁](https://researchlife.vercel.app/)上時卻總是無法正常的顯示為兩欄的形式。

這個問題困擾了我幾天。因為我對於網頁架設並不熟悉。網頁的架設也是使用obsidian的外掛[digital garden](https://dg-docs.ole.dev/)所完成的。但是在[digital garden](https://dg-docs.ole.dev/)的說明頁面也只有寫如何自訂CSS，並沒有提到我所遇到的困難。而我也不知道問題到底出在哪？是CSS沒有寫好呢？還是網頁的架設配置有問題。

我試著詢問🤖

> 👨：I use a custom css in my blog build with the obsidian digital garden. the css file is downloaded from https://github.com/efemkay/obsidian-modular-css-layout. according to the instruction of digital garden (https://dg-docs.ole.dev/), I put the css file in user defined css folder. However, the [!multi-column] format is not correctly functioning. any idea how to solve my problem? 

結果得到的回應是CSS設置的方式，要放到正確的資料夾，html的head標籤裡需要設定好連結。這些都是確定有完成的。接著我又詢問了幾次，問看看有沒有其他的可能性，然而都沒有成功。

後來我再仔細地看了一下網頁的原始碼，發現我的markdown語法並沒有被轉換為正確的html標籤。我的**multi-column callout都變成了blockquote**。而這個發現終於成為解決問題的關鍵。

在和機器人的一般詢問之後，我知道了我使用的vercel要先透過一個static site generator (SSG)，將我的markdown筆記轉為html。應該就是這個轉換過程出了問題。

接著在機器人的介紹之下，我知道了幾個常見的SSG，並在比對之下我找到了我所使用的SSG，是Eleventy，裡面是用javascript寫的。

於是我在我的github裡面找到了Eleventy的執行語法，接著在上面搜尋有關callout的片段。再把相關的片段貼給🤖，請它解釋這個片段在做什麼。

經過一番努力，終於發現是這個片段造成了問題

> The following code block checks if the content of the blockquote matches the callout block using a regular expression:

``` javascript
const calloutMeta = /\[!(\w*)\](\+|\-){0,1}(\s?.*)/;
if (!content.match(calloutMeta)) {
  continue;
}
```


> 🤖：The regular expression /\[!(\w*)\](\+|\-){0,1}(\s?.\*)/ matches strings that start with ![ and followed by any word characters, then may or may not be followed by a + or - symbol, and then followed by any number of spaces and characters.
> 🤖： The if statement checks if the content string matches this regular expression. If it does not match, the script moves on to the next blockquote.


從🤖的說明上，我覺得`[!multi-column]`應該是符合才對啊！於是我直接問它`[!multi-column]`是不是符合。結果竟然不符合！！！原因是「-」不是word characters……regular expression用時方恨少啊…

但都到這一步，那麼下一步就很簡單了，我請他幫我把這一小段改為可以把`[!multi-column]`判斷為callout，但是要保留本來這一段的功能。

🤖也很快的給出了答案

> 🤖： Sure, you can modify the regular expression to allow hyphens - in the callout name by changing the (\w*) part to ([\w-]\*).




> [!multi-column]
>
>> [!info] 真的是
>
>> [!info] 太棒了