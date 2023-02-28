---
{"dg-publish":true,"permalink":"/notes/obsidian digital garden使用事項/","title":"digital garden使用注意事項","tags":["plugin","webpage"]}
---


### 使用中文檔名

- 若是檔名是中文，生成連結時預設會將中文去掉。故若資料夾當中同時有兩個以上的筆記檔名都只有中文，那麼生成連結時會變成兩個筆記有相同的連結，因為中文都被去掉了。這時有幾種解法
  - 將筆記的檔名改為英文
  - 在fronter當中設定連結 `dg-permalink: "中文名稱"`
  - turn off note setting當中的slugify note url。使用這個方法就不會自動產生去掉非英文字母的連結了。

### 使用[Modular CSS Layout for Obsidian](https://github.com/efemkay/obsidian-modular-css-layout)

若要使用[Modular CSS Layout for Obsidian](https://github.com/efemkay/obsidian-modular-css-layout)，因為`[!multi-column]`不會被成功辨識為是callout，而會被轉為blockquote。原因是「-」不是word characters。這時要去修改github當中根目錄底下的.eleventy.js

把原來的

```javascript
const calloutMeta = /\[!(\w*)\](\+|\-){0,1}(\s?.*)/;
if (!content.match(calloutMeta)) {
  continue;
}
```

修改為

```javascript
const calloutMeta = /\[!([\w-]*)\](\+|\-){0,1}(\s?.*)/;
if (!content.match(calloutMeta)) {
  continue;
}
```

詳見[[Blog/Life/ChatGPT可以幫我改code\|ChatGPT可以幫我改code]]

### 使用google fonts

先在`src/site/_includes/components/user/common/head/`當中加入新的檔案，例如`googlefont.njk`

```
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC&family=Noto+Serif+TC&display=swap" rel="stylesheet">
```

再在`src/site/styles/user/`裡面新增.css檔。.theme會修改整體的文字。

```
h1, h2, h3 {
    font-family: 'Noto Serif TC', serif; 
}
.theme-dark {
    background: var(--background-primary);
    color: var(--text-normal);
    font-family: 'Noto Sans TC', sans-serif;
}

.theme-light {
    background: white;
    color: black;
    font-family: 'Noto Sans TC', sans-serif;
}
```
