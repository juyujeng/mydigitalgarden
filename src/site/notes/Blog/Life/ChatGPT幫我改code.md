---
{"dg-publish":true,"permalink":"/Blog/Life/ChatGPT幫我改code/","title":"ChatGPT幫我改code","tags":["blog","ai","webpage","coding"]}
---


# ChatGPT幫我改code

obsidian有很好用的CSS片段叫做[Modular CSS Layout for Obsidian](https://github.com/efemkay/obsidian-modular-css-layout)，它可以很方便地將筆記段落排版為多欄位的形式。在我的電腦上使用起來完全沒有問題，但是當我把筆記放到網頁上時卻總是無法正常的將markdown語法轉換為正確的html標籤。我的multi-column callout都變成了blockquote。

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