---
{"dg-publish":true,"permalink":"/可接續的 AI 專案工作流/","title":"可接續的 AI 專案工作流","tags":["LLMAI","ai"],"created":"2026-08-14T16:13","updated":"2026-08-17T23:47","dg-note-properties":{"date":"2026-08-14T16:13","lastmod":"2026-08-17T23:47","tags":["LLMAI","ai"],"title":"可接續的 AI 專案工作流","theme":"css/mida-theme.css","center":true,"height":1080,"width":1920}}
---

<!-- slide class="title-page" -->
# 可接續的 AI 專案工作流

換 Agent、換電腦，不必重零開始

朱玉正

---

## 可接續的 AI 工作適用情境

- 在家裡的電腦想要接續完成研究室中未完成的任務
- 目前的AI agent工作額度快用完了，需要其他agent接手

> [!caution] 但是我不想、也沒辦法從頭到尾再仔細說明所有需求、流程與進度！




---

## 可接續性來自三個支柱

| 三個支柱        | 目的                     | 功能                                       |
| ----------- | ---------------------- | ---------------------------------------- |
| **Skills**  | 工作 SOP                 | 就算換Agent，仍然按照固定的流程完成工作                   |
| **外部化專案記憶** | 記錄專案脈絡（專案手冊＋研究紀錄＋交接簿等） | 提供Agent工作需要的資訊，不需要重複說明。例如背景資訊、目前進度、關鍵詞等。 |
| **雲端硬碟**    | 共用相關檔案櫃                | 同步不同電腦間工作的所有資料                           |

> [!IMPORTANT] 可接續的 AI 工作＝相同工作SOP＋相同專案脈絡＋相同檔案


---

## 1｜Skills：把工作方法寫成可重複執行的 SOP

Skill 是一組可重複使用的**工作流程**，可以包含：

- 執行步驟與完成條件
- 需要查閱的參考資料
- 可重複執行的本機程式
- 成果範本與其他資源

> [!NOTE] 安裝或建立skills
> Agent可以協助安裝或是自行建立
> `個人skills`：安裝於系統使用者資料夾，所有專案都可以使用
> `專案skills`：安裝於專案資料夾，只有該專案可以使用

---
## 2｜外部化專案記憶：讓新 Agent 重建脈絡

外部化專案記憶是==一組文字檔案==，記錄專案脈絡資訊：

- **規則**：哪些行為必須遵守？
- **目標**：這個專案要完成什麼？
- **共同語言**：專有名詞代表什麼？
- **判準**：如何判斷品質與完成？
- **決策**：重要選擇是什麼？為什麼？
- **狀態**：目前完成什麼？下一步是什麼？

> [!NOTE] 如何建立外部化專案記憶檔案
> 現在大多skills都有自己搭配的外部化文件，會自動撰寫


---

## 3｜雲端硬碟：讓不同電腦看到同一個專案現況

<split even gap="5">
> [!NOTE] 可一起同步的資料：
> - 來源資料、衍生資料與正式產物
> - `AGENTS.md` 與外部化專案記憶
> - `.agents/skills/` 內的專案專用 skills
> - 交接紀錄與驗證結果

> [!CAUTION] 不會同步的內容包括：
> - 先前的對話記憶
> - 只安裝在某台電腦上的個人 skills
> - 該電腦特有的軟體、權限與環境設定
</split>

---

## AI接續工作流程

<style> .container {font-family: sans-serif; text-align: center;} .button-wrapper button {z-index: 1;height: 40px; width: 100px; margin: 10px;padding: 5px;} .excalidraw .App-menu_top .buttonList { display: flex;} .excalidraw-wrapper { height: 800px; margin: 50px; position: relative;} :root[dir="ltr"] .excalidraw .layer-ui__wrapper .zen-mode-transition.App-menu_bottom--transition-left {transform: none;} </style><script src="https://cdn.jsdelivr.net/npm/react@17/umd/react.production.min.js"></script><script src="https://cdn.jsdelivr.net/npm/react-dom@17/umd/react-dom.production.min.js"></script><script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@excalidraw/excalidraw@0/dist/excalidraw.production.min.js"></script><div id="AI工作可接續性的工作流程excalidraw.md1"></div><script>(function(){const InitialData={"type":"excalidraw","version":2,"source":"https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.26.4","elements":[{"id":"urTmIwvE","type":"rectangle","x":-322.26213888862185,"y":-296.16321824600146,"width":205.05776977539062,"height":62.37141418457031,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#ffc9c9","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a7","roundness":{"type":3},"seed":1515267985,"version":474,"versionNonce":207853055,"isDeleted":false,"boundElements":[{"type":"text","id":"YXZFUssd"},{"id":"JSrhwJeJ","type":"arrow"}],"updated":1786981157782,"link":null,"locked":false,"hasTextLink":false},{"id":"YXZFUssd","type":"text","x":-315.645226046825,"y":-284.9775111537163,"width":191.82394409179688,"height":40,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a8","roundness":null,"seed":643061360,"version":410,"versionNonce":1977765489,"isDeleted":false,"boundElements":[],"updated":1786981142706,"locked":false,"text":"在A電腦中設定需要的skills\n與外部化專案記憶檔案","rawText":"在A電腦中設定需要的skills與外部化專案記憶檔案","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"urTmIwvE","originalText":"在A電腦中設定需要的skills與外部化專案記憶檔案","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"WBzSJRmt","type":"rectangle","x":-186.0156399841229,"y":126.86362537942057,"width":254.73012562906717,"height":95.43062335248158,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#ffec99","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aD","roundness":{"type":3},"seed":2140155536,"version":133,"versionNonce":1450274960,"isDeleted":false,"boundElements":[{"type":"text","id":"RU8w5qfA"},{"id":"dy94bRiv","type":"arrow"},{"id":"m14h1G3I","type":"arrow"},{"id":"QADTLgw3","type":"arrow"},{"id":"O2agjXI7","type":"arrow"}],"updated":1786722998624,"link":null,"locked":false,"hasTextLink":false},{"id":"RU8w5qfA","type":"text","x":-114.65057716958933,"y":154.57893705566136,"width":112,"height":40,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aE","roundness":null,"seed":1647176816,"version":73,"versionNonce":156689520,"isDeleted":false,"boundElements":[],"updated":1786722854440,"locked":false,"text":"使用雲端硬碟\n同步專案資料夾","rawText":"使用雲端硬碟\n同步專案資料夾","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"WBzSJRmt","originalText":"使用雲端硬碟\n同步專案資料夾","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"AONrqtgI","type":"rectangle","x":-410.7677061097002,"y":-193.1248373948947,"width":277.5610980986125,"height":258.9633374570437,"angle":0,"strokeColor":"#e03131","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aF","roundness":{"type":3},"seed":670625936,"version":217,"versionNonce":251171440,"isDeleted":false,"boundElements":[],"updated":1786722852133,"link":null,"locked":false,"hasTextLink":false},{"id":"TP5dIjEQ","type":"rectangle","x":-357.4143457303765,"y":-129.5119212936292,"width":187.10632367253666,"height":71.0863723470726,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aG","roundness":{"type":3},"seed":1232245392,"version":326,"versionNonce":2036343440,"isDeleted":false,"boundElements":[{"type":"text","id":"qAM8oWxU"},{"id":"orvqxajp","type":"arrow"},{"id":"JSrhwJeJ","type":"arrow"},{"id":"O2agjXI7","type":"arrow"}],"updated":1786723003224,"link":null,"locked":false,"hasTextLink":false},{"id":"qAM8oWxU","type":"text","x":-335.8611838941082,"y":-113.9687351200929,"width":144,"height":40,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aH","roundness":null,"seed":1012840592,"version":253,"versionNonce":1407891056,"isDeleted":false,"boundElements":[],"updated":1786722852133,"locked":false,"text":"使用skills讀取\n外部化專案記憶檔案","rawText":"使用skills讀取\n外部化專案記憶檔案","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"TP5dIjEQ","originalText":"使用skills讀取\n外部化專案記憶檔案","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"-uL-_6pZA4-EFAm5pKPCJ","type":"rectangle","x":-368.06618370163585,"y":-26.333573211355827,"width":208.40999961505526,"height":71.0863723470726,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aI","roundness":{"type":3},"seed":576983152,"version":328,"versionNonce":2076107408,"isDeleted":false,"boundElements":[{"type":"text","id":"2GY4f2ep"},{"id":"orvqxajp","type":"arrow"},{"id":"dy94bRiv","type":"arrow"}],"updated":1786722882903,"link":null,"locked":false,"hasTextLink":false},{"id":"2GY4f2ep","type":"text","x":-359.8611838941082,"y":-10.790387037819528,"width":192,"height":40,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aJ","roundness":null,"seed":510165616,"version":261,"versionNonce":363059824,"isDeleted":false,"boundElements":[],"updated":1786722852133,"locked":false,"text":"使用skills進行工作\n並更新外部化專案記憶檔案","rawText":"使用skills進行工作\n並更新外部化專案記憶檔案","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"-uL-_6pZA4-EFAm5pKPCJ","originalText":"使用skills進行工作\n並更新外部化專案記憶檔案","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"orvqxajp","type":"arrow","x":-263.84207496262496,"y":-52.4255489465566,"width":0.0013337693623043378,"height":20.091975735200776,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aK","roundness":{"type":2},"seed":2025651824,"version":137,"versionNonce":1136923217,"isDeleted":false,"boundElements":[],"updated":1786981033453,"link":null,"locked":false,"points":[[0,0],[0.0013337693623043378,20.091975735200776]],"startBinding":{"elementId":"TP5dIjEQ","mode":"orbit","fixedPoint":[0.5001,1]},"endBinding":{"elementId":"-uL-_6pZA4-EFAm5pKPCJ","mode":"orbit","fixedPoint":[0.5001,0]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":false,"moveMidPointsWithElement":false,"hasTextLink":false},{"id":"p3BU0uYg","type":"text","x":-392.31338464181493,"y":-182.14410097379,"width":138.45994567871094,"height":25,"angle":0,"strokeColor":"#e03131","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["aurU_sJ04nSuCchquwy50"],"frameId":null,"index":"aL","roundness":null,"seed":1175898736,"version":156,"versionNonce":241434224,"isDeleted":false,"boundElements":[],"updated":1786722852134,"locked":false,"text":"A 電腦的Agent","rawText":"A 電腦的Agent","fontSize":20,"fontFamily":5,"textAlign":"left","verticalAlign":"top","containerId":null,"originalText":"A 電腦的Agent","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"eCa4-rNUAqFJR-RdSlJC8","type":"rectangle","x":4.9756119226175315,"y":-196.40376715471768,"width":277.5610980986125,"height":258.9633374570437,"angle":0,"strokeColor":"#2f9e44","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aM","roundness":{"type":3},"seed":1304417424,"version":274,"versionNonce":1688965744,"isDeleted":false,"boundElements":[],"updated":1786722840062,"link":null,"locked":false,"hasTextLink":false},{"id":"voZCDfZkxXpvXj7BLhsG9","type":"rectangle","x":58.328972301941235,"y":-132.49552393940212,"width":187.10632367253666,"height":71.0863723470726,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aN","roundness":{"type":3},"seed":1308017296,"version":379,"versionNonce":1074571647,"isDeleted":false,"boundElements":[{"type":"text","id":"pDfMDlQC"},{"id":"S70v8A7FFIBXLsmEqSUM_","type":"arrow"},{"id":"m14h1G3I","type":"arrow"},{"id":"6SrrbqOV","type":"arrow"}],"updated":1786981215654,"link":null,"locked":false,"hasTextLink":false},{"id":"pDfMDlQC","type":"text","x":79.88213413820957,"y":-116.95233776586582,"width":144,"height":40,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aO","roundness":null,"seed":1159721104,"version":309,"versionNonce":1500410385,"isDeleted":false,"boundElements":[],"updated":1786981033455,"locked":false,"text":"使用skills讀取\n外部化專案記憶檔案","rawText":"使用skills讀取\n外部化專案記憶檔案","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"voZCDfZkxXpvXj7BLhsG9","originalText":"使用skills讀取\n外部化專案記憶檔案","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"56w-HTUGm6gC-g83Orcrq","type":"rectangle","x":47.677134330681895,"y":-29.317175857128746,"width":208.40999961505526,"height":71.0863723470726,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aP","roundness":{"type":3},"seed":452157072,"version":383,"versionNonce":1184580208,"isDeleted":false,"boundElements":[{"type":"text","id":"JoCSVmhT"},{"id":"S70v8A7FFIBXLsmEqSUM_","type":"arrow"},{"id":"QADTLgw3","type":"arrow"}],"updated":1786722907724,"link":null,"locked":false,"hasTextLink":false},{"id":"JoCSVmhT","type":"text","x":55.88213413820952,"y":-13.773989683592447,"width":192,"height":40,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aQ","roundness":null,"seed":2690192,"version":317,"versionNonce":877912529,"isDeleted":false,"boundElements":[],"updated":1786981033456,"locked":false,"text":"使用skills進行工作\n並更新外部化專案記憶檔案","rawText":"使用skills進行工作\n並更新外部化專案記憶檔案","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"56w-HTUGm6gC-g83Orcrq","originalText":"使用skills進行工作\n並更新外部化專案記憶檔案","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"S70v8A7FFIBXLsmEqSUM_","type":"arrow","x":151.90124306969278,"y":-55.409151592329515,"width":0.0013337693623043378,"height":20.09197573520077,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aR","roundness":{"type":2},"seed":1316551312,"version":192,"versionNonce":2144864241,"isDeleted":false,"boundElements":[],"updated":1786981033456,"link":null,"locked":false,"points":[[0,0],[0.0013337693623043378,20.09197573520077]],"startBinding":{"elementId":"voZCDfZkxXpvXj7BLhsG9","mode":"orbit","fixedPoint":[0.5001,1]},"endBinding":{"elementId":"56w-HTUGm6gC-g83Orcrq","mode":"orbit","fixedPoint":[0.5001,0]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":false,"moveMidPointsWithElement":false,"hasTextLink":false},{"id":"Rr5wFpcv","type":"text","x":23.42993339050281,"y":-185.1277036195629,"width":140.15994262695312,"height":25,"angle":0,"strokeColor":"#2f9e44","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":["iKplxFFHxgwZ8d0TjSGk2"],"frameId":null,"index":"aS","roundness":null,"seed":1754998928,"version":214,"versionNonce":8361616,"isDeleted":false,"boundElements":[],"updated":1786722842690,"locked":false,"text":"B 電腦的Agent","rawText":"B 電腦的Agent","fontSize":20,"fontFamily":5,"textAlign":"left","verticalAlign":"top","containerId":null,"originalText":"B 電腦的Agent","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"JSrhwJeJ","type":"arrow","x":-219.83325400092656,"y":-227.79180406143115,"width":81.82549166852317,"height":92.27988276780195,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#a5d8ff","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aT","roundness":null,"seed":280386704,"version":409,"versionNonce":1735063615,"isDeleted":false,"boundElements":[],"updated":1786981234436,"link":null,"locked":false,"points":[[0,0],[0,13.157078571612232],[37.69756177534151,13.157078571612232],[37.69756177534151,73.83219888888644],[-44.12792989318166,73.83219888888644],[-44.12792989318166,92.27988276780195]],"startBinding":{"elementId":"urTmIwvE","mode":"orbit","fixedPoint":[0.4995123325484835,1.0961979149974814]},"endBinding":{"elementId":"TP5dIjEQ","mode":"orbit","fixedPoint":[0.4994655445201572,-0.08440436333852512]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":true,"hasTextLink":false,"moveMidPointsWithElement":false,"fixedSegments":[{"index":2,"start":[0,13.157078571612232],"end":[37.69756177534151,13.157078571612232]},{"index":3,"start":[37.69756177534151,13.157078571612232],"end":[37.69756177534151,73.83219888888644]},{"index":4,"start":[37.69756177534151,73.83219888888644],"end":[-44.12792989318166,73.83219888888644]}],"startIsSpecial":false,"endIsSpecial":false},{"id":"dy94bRiv","type":"arrow","x":-263.9611838941082,"y":50.75279913571677,"width":191.2300614049678,"height":70.11082624370381,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#a5d8ff","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aU","roundness":null,"seed":1528617104,"version":181,"versionNonce":1359445104,"isDeleted":false,"boundElements":[],"updated":1786723096788,"link":null,"locked":false,"points":[[0,0],[0,35.0554131218519],[191.2300614049678,35.0554131218519],[191.2300614049678,70.11082624370381]],"startBinding":{"elementId":"-uL-_6pZA4-EFAm5pKPCJ","mode":"orbit","fixedPoint":[0.49952017657413417,1.0844043633385252]},"endBinding":{"elementId":"WBzSJRmt","mode":"orbit","fixedPoint":[0.44472367457606926,-0.06287289959155404]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":true,"fixedSegments":null,"startIsSpecial":null,"endIsSpecial":null,"hasTextLink":false},{"id":"m14h1G3I","type":"arrow","x":-58.75057716958932,"y":120.86362537942058,"width":111.07954947153056,"height":217.91596314528638,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#a5d8ff","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aV","roundness":null,"seed":166882448,"version":66,"versionNonce":274324112,"isDeleted":false,"boundElements":[],"updated":1786722901320,"link":null,"locked":false,"points":[[0,0],[0,-217.91596314528638],[111.07954947153056,-217.91596314528638]],"startBinding":{"elementId":"WBzSJRmt","mode":"orbit","fixedPoint":[0.4996074276658364,-0.06287289959155404]},"endBinding":{"elementId":"voZCDfZkxXpvXj7BLhsG9","mode":"orbit","fixedPoint":[-0.032067328790559076,0.4985932606110249]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":true,"fixedSegments":null,"startIsSpecial":null,"endIsSpecial":null,"hasTextLink":false},{"id":"QADTLgw3","type":"arrow","x":151.78213413820953,"y":47.76919648994385,"width":210.53271130779885,"height":220.5250522419583,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#a5d8ff","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aW","roundness":null,"seed":1566256240,"version":178,"versionNonce":2123115120,"isDeleted":false,"boundElements":[],"updated":1786723063244,"link":null,"locked":false,"points":[[0,0],[0,220.5250522419583],[-210.53271130779885,220.5250522419583],[-210.53271130779885,180.5250522419583]],"startBinding":{"elementId":"56w-HTUGm6gC-g83Orcrq","mode":"orbit","fixedPoint":[0.49952017657413417,1.0844043633385252]},"endBinding":{"elementId":"WBzSJRmt","mode":"orbit","fixedPoint":[0.4996074276658364,1.0628728995915542]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":true,"fixedSegments":null,"startIsSpecial":null,"endIsSpecial":null,"hasTextLink":false},{"id":"O2agjXI7","type":"arrow","x":-73.12599233140148,"y":228.29424873190214,"width":370.07477616401786,"height":362.362983851995,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#a5d8ff","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aY","roundness":null,"seed":1839507088,"version":356,"versionNonce":1560254559,"isDeleted":false,"boundElements":[],"updated":1786981234436,"link":null,"locked":false,"points":[[0,0],[0,40],[-370.07477616401786,40],[-370.07477616401786,-322.362983851995],[-290.288353398975,-322.362983851995]],"startBinding":{"elementId":"WBzSJRmt","mode":"orbit","fixedPoint":[0.4431735248193967,1.0628728995915542]},"endBinding":{"elementId":"TP5dIjEQ","mode":"orbit","fixedPoint":[-0.032067328790559076,0.49859326061102505]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":true,"fixedSegments":[{"index":3,"start":[-370.07477616401786,40],"end":[-370.07477616401786,-322.362983851995]}],"startIsSpecial":true,"endIsSpecial":false,"hasTextLink":false},{"id":"a1V4Y0W2nXdSZhLA1biIs","type":"rectangle","x":23.27736150294504,"y":-301.06335157582885,"width":236.54289050737097,"height":90,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#b2f2bb","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aZ","roundness":{"type":3},"seed":990471665,"version":619,"versionNonce":2114282879,"isDeleted":false,"boundElements":[{"type":"text","id":"dhsjAtce"},{"id":"6SrrbqOV","type":"arrow"}],"updated":1786981213251,"link":null,"locked":false,"hasTextLink":false},{"id":"dhsjAtce","type":"text","x":28.956834405556307,"y":-286.06335157582885,"width":225.18394470214844,"height":60,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aa","roundness":null,"seed":2108260305,"version":659,"versionNonce":1626173201,"isDeleted":false,"boundElements":[],"updated":1786981123173,"locked":false,"text":"在B電腦中安裝需要的個人skills\n※專案skills在資料夾同步後自\n動安裝","rawText":"在B電腦中安裝需要的個人skills\n※專案skills在資料夾同步後自動安裝","fontSize":16,"fontFamily":5,"textAlign":"center","verticalAlign":"middle","containerId":"a1V4Y0W2nXdSZhLA1biIs","originalText":"在B電腦中安裝需要的個人skills\n※專案skills在資料夾同步後自動安裝","autoResize":true,"lineHeight":1.25,"hasTextLink":false,"link":null},{"id":"6SrrbqOV","type":"arrow","x":141.44880675663055,"y":-205.06335157582888,"width":79.25664109054279,"height":66.56782763642678,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#ffc9c9","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"ab","roundness":null,"seed":1515808031,"version":243,"versionNonce":302927007,"isDeleted":false,"boundElements":[],"updated":1786981234437,"link":null,"locked":false,"points":[[0,0],[0,14.783556785188466],[79.25664109054279,14.783556785188466],[79.25664109054279,49.925870727320074],[10.33332738157901,49.925870727320074],[10.33332738157901,66.56782763642678]],"startBinding":{"elementId":"a1V4Y0W2nXdSZhLA1biIs","mode":"orbit","fixedPoint":[0.49957724368808765,1.0666666666666664]},"endBinding":{"elementId":"voZCDfZkxXpvXj7BLhsG9","mode":"orbit","fixedPoint":[0.4994655445201573,-0.08440436333852472]},"startArrowhead":null,"endArrowhead":"arrow","elbowed":true,"fixedSegments":[{"index":2,"start":[0,14.783556785188466],"end":[79.25664109054279,14.783556785188466]},{"index":3,"start":[79.25664109054279,14.783556785188466],"end":[79.25664109054279,49.925870727320074]}],"startIsSpecial":false,"endIsSpecial":false,"hasTextLink":false}],"appState":{"theme":"light","viewBackgroundColor":"#ffffff","currentItemStrokeColor":"#1e1e1e","currentItemBackgroundColor":"#ffc9c9","currentItemFillStyle":"solid","currentItemStrokeWidthKey":"medium","currentItemStrokeVariability":"constant","currentItemStrokeStyle":"solid","currentItemRoughness":1,"currentItemOpacity":100,"currentItemFontFamily":5,"currentItemFontSize":20,"currentItemTextAlign":"left","currentItemStartArrowhead":null,"currentItemEndArrowhead":"arrow","currentItemArrowType":"elbow","currentItemFrameRole":null,"scrollX":463.0174425144651,"scrollY":368.4486445015127,"zoom":{"value":1},"currentItemRoundness":"round","gridSize":20,"gridStep":5,"gridModeEnabled":false,"gridColor":{"Bold":"rgba(217, 217, 217, 0.5)","Regular":"rgba(230, 230, 230, 0.5)"},"currentStrokeOptions":null,"frameRendering":{"enabled":true,"clip":true,"name":true,"outline":true,"markerName":true,"markerEnabled":true},"objectsSnapModeEnabled":false,"activeTool":{"type":"selection","customType":null,"locked":false,"fromSelection":false,"lastActiveTool":null},"disableContextMenu":false,"bindingPreference":"enabled","isBindingEnabled":true,"isMidpointSnappingEnabled":true,"boxSelectionMode":"contain"},"files":{}};InitialData.scrollToContent=true;App=()=>{const e=React.useRef(null),t=React.useRef(null),[n,i]=React.useState({width:void 0,height:void 0});return React.useEffect(()=>{i({width:t.current.getBoundingClientRect().width,height:t.current.getBoundingClientRect().height});const e=()=>{i({width:t.current.getBoundingClientRect().width,height:t.current.getBoundingClientRect().height})};return window.addEventListener("resize",e),()=>window.removeEventListener("resize",e)},[t]),React.createElement(React.Fragment,null,React.createElement("div",{className:"excalidraw-wrapper",ref:t},React.createElement(ExcalidrawLib.Excalidraw,{ref:e,width:n.width,height:n.height,initialData:InitialData,viewModeEnabled:!0,zenModeEnabled:!0,gridModeEnabled:!1})))},excalidrawWrapper=document.getElementById("AI工作可接續性的工作流程excalidraw.md1");ReactDOM.render(React.createElement(App),excalidrawWrapper);})();</script>

---

## 在交棒前要確認的事：

- **同步**：檔案已完成同步，交接檔避免同時由兩端修改。
- 必要軟體、個人 skills 是否可用。


---

<!-- slide class="chapter-page" -->
# 實例



---

## GKCSAF回饋考官專案



> [!abstract] 專案目的
> 
> 1. 執行GKCSAF回饋考官並產生回饋文件
> 2. 審查回饋考官產生的回饋文件
> 3. 記錄工作狀況，並產生進度報告（會議記錄、會議簡報）


---
## 用到的Skills

### 全域skills

<div class="card-container" style="grid-template-columns: repeat(2, 1fr); text-align: left;">

<div class="card">

### writing-for-agents
協助建立`AGENTS.md`

</div>

<div class="card">

### grill-with-docs
協助釐清目的以及重要決策，並建立需要的外部記憶文件

</div>

</div>

### 自己建立的專案skills

<div class="card-container" style="grid-template-columns: repeat(2, 1fr); text-align: left;">

<div class="card">

### 標準化逐字稿
將原始逐字稿`.docx`檔轉為方便回饋考官處理的`.md`檔

</div>

<div class="card">

### GKCSAF虛擬回饋考官
根據評分/回饋規則，分析標準化逐字稿的內容並提供評分/回饋報告。

</div>

<div class="card">

### 回饋品質審查
根據審查規則評估「GKCSAF虛擬回饋考官」的回饋報告，並按照固定格式輸出審查報告。

</div>

<div class="card">

### 進度報告產生器
讀取目前的成果以及比對事先設定的進度規畫，按照固定的格式產生會議記錄（`.docx`）以及會議簡報（`.pptx`）。

</div>

</div>


---
## 資料夾結構與外部化專案記憶文件

```text
GKCSAF 回饋考官/
├── AGENTS.md                  # 專案工作規則與資料界線
├── PROJECT.md                 # 目標、角色與整體流程
├── CONTEXT.md                 # 重要名詞
├── RUBRIC.md                  # 評分與品質判準
├── docs/adr/                  # 重要決策與理由
└── .agents/
    ├── handoff/CURRENT.md     # 目前狀態與下一步
    └── skills/
        ├── gkcsaf-standardize-transcripts/
        ├── gkcsaf-generate-feedback/
        ├── gkcsaf-review-feedback/
        └── gkcsaf-meeting-package/
```

> [!IMPORTANT] 資料結構僅供參考，應按各專案需求調整

---

## 外部化專案記憶文件的功能

| 功能         | GKCSAF 使用的檔案                 | 使用的時機            |
| ---------- | ---------------------------- | ---------------- |
| 專案規則與資料界線  | `AGENTS.md`                  | 新任務每次都要先閱讀       |
| 目標、角色與整體流程 | `PROJECT.md`                 | 回顧專案全貌           |
| 關鍵詞彙       | `CONTEXT.md`                 | 撰寫文件時，避免關鍵詞被不同解讀 |
| 評估與品質判準    | `RUBRIC.md`                  | 評估成品             |
| 記錄重要決策與理由  | `docs/adr/`                  | 決策難以逆轉且存在真實取捨    |
| 目前狀態與下一步   | `.agents/handoff/CURRENT.md` | 工作會跨任務或跨電腦接續     |

在 Codex 中，`AGENTS.md` 是會被自動讀取的專案指引入口；其他文件可由 `AGENTS.md` 或 skills 清楚指定，要求閱讀。

---

## 實例：`AGENTS.md` 讓新 Agent 知道從哪裡開始

```markdown
## 每次開始前

- 先讀 `PROJECT.md`、`CONTEXT.md`、`RUBRIC.md`
  與 `.agents/handoff/CURRENT.md`。
- 涉及重要流程或研究口徑時，查閱 `docs/adr/`
  中未被取代的決策。

## 資料界線

- 只處理使用者當次明確指定的檔案、資料夾或案例；
  不自行擴大範圍。

## 研究產物規則

- 完成任務後更新 `.agents/handoff/CURRENT.md`，
  但不寫入識別資訊或個案引文。
```

`AGENTS.md` 不必塞進全部知識；它可以告訴 Codex **何時應讀哪一份權威文件**。

---
## 實例：`CONTEXT.md` 讓新 Agent 知道關鍵詞

```text
# GKCSAF 虛擬回饋考官

本專案發展並驗證以大型語言模型為基礎的臨床溝通技能虛擬回饋考官。

## Language

**虛擬回饋考官**：
依 GKCSAF 評估逐字稿中醫療專業人員的溝通表現，並提供形成性文字回饋的虛擬考官。
_Avoid_: 虛擬評分員、GPT 評分考官

**全新獨立評分**：
在未接觸任何既有回饋、審查、正式專家評分或先前產生對話的全新任務中，針對一個參與者案例完成一次評分。
_Avoid_: 同一對話再評一次、參考前次結果重評

**評分複本（rating replicate）**：
全新獨立評分成功凍結後形成的一個不可變觀測；同一參與者的複本以 `r001`、`r002` 依序識別，彼此平行且不互相取代。
_Avoid_: 回饋修訂版、評分平均

**回饋品質**：
虛擬回饋考官所產生回饋在對應性、完整性/深度、可行性、清晰易懂與實用價值五方面的表現。
```


---
## 實例：`PROJECT.md` 讓新 Agent 知道專案脈絡

```text
# GKCSAF 虛擬回饋考官專案

## 目的

發展並驗證以大型語言模型為基礎的臨床溝通技能虛擬回饋考官。系統依 GKCSAF 評估實習生或治療師的醫病溝通表現，產生可追溯、精簡且可執行的形成性回饋，再由獨立 AI 審查員與正式專家平行驗證回饋品質。

## 研究單位與角色

- **參與者案例**：一位參與者及其兩份相關逐字稿。
- **虛擬回饋考官**：在全新獨立任務中綜合兩份逐字稿，一次完成九個 GKCSAF 向度與一個評分複本。
- **AI 審查員**：在新的獨立執行中，依五項品質向度與 QuAL 審查一個已凍結回饋產物。
- **正式專家**：另行招募的人類臨床教育專家，依研究程序完成正式評分。
- **會議文件幫手**：產生會議簡報、會議記錄及對應 Markdown 草稿，不處理個案回饋。

## 標準工作流

1. 使用者明確指定需轉換的 Word 檔或資料夾。
2. 本機程式保留原文與段落順序，產生具發言編號、metadata 與 SHA-256 的標準化 Markdown。
3. 使用者在全新任務指定一位參與者；虛擬回饋考官不讀既有評分結果，依 `transcript_id` 固定順序確認來源及受評者，完成九向度綜合評分。
4. 模型只在臨時檔寫證據代碼；本機程式驗證後展開引文，並在成功時配置該參與者下一個 `rNNN`，以不可覆寫方式建立凍結回饋。失敗或中止不消耗編號。
5. AI 審查員及正式專家從同一凍結回饋平行評分；不共用對話歷史、其他審查結果或產生者推理。
6. 每次新的評分要求另開全新任務並建立下一個評分複本；回饋考官不比較複本、不控制重複次數，也不計算信度。
```

---

<!-- slide class="chapter-page" -->
# 會後自學

以下頁面提供建立步驟、推薦 skills 與可直接修改的提示詞。

---

## 先找現成 skill，再決定是否自己建立

建議順序：

1. 用 `$find-skills` 說明自己的任務與需求。
2. 到 [skills.sh](https://www.skills.sh/) 或使用 Skills CLI 搜尋。
3. 檢查來源、安裝量、儲存庫、內容與安全稽核。
4. 安裝後先用低風險任務測試。
5. 找不到合適流程，再用 `$skill-creator` 建立自己的 skill。

```text
$find-skills 請幫我找可以協助＿＿＿＿的 skill。
我的工作情境是＿＿＿＿，需要產出＿＿＿＿，
而且必須遵守＿＿＿＿的資料或品質限制。
```



---

## 我的入門推薦

<div class="card-container" style="grid-template-columns: repeat(2, 1fr); text-align: left;">

<div class="card">

### `$grill-me`

- 一次只問一個需要人決定的問題。
- 逐一釐清相依的選擇，直到形成共同理解。
- 適合規劃研究流程、簡報、分析計畫或系統設計。

</div>

<div class="card">

### `$grill-with-docs`

- 在同樣的訪談過程中加入 `domain-modeling`。
- 釐清共同語言，並在必要時記錄重要決策。
- 適合需要長期維護專案文件的工作。

</div>

<div class="card">

### `$writing-for-agents`

協助改善 Agent 會讀取的文件：

- 讓步驟有清楚、可檢查的完成條件。
- 用簡短而精確的指引指向外部參考資料。
- 把共通知識維持在單一權威來源。
- 移除重複、過時或不會改變行為的文字。

</div>

</div>

---

## 沒有合適的現成流程，再建立自己的 skill

### `$skill-creator`

協助建立或更新 skill，包括：

1. 用具體案例界定任務。
2. 定義何時應啟動、何時不應啟動。
3. 決定需要指引、scripts、references 或 assets。
4. 建立 `SKILL.md` 與必要資源。
5. 驗證結構並以真實任務反覆改進。


> 參考：[OpenAI｜Create a skill](https://learn.chatgpt.com/docs/build-skills#create-a-skill)

---

## 一個最小起始結構

<split left="6" right="4" gap="2">

```text
my-research-project/
├── AGENTS.md
├── PROJECT.md
├── sources/
├── outputs/
└── .agents/
    ├── skills/
    │   └── my-workflow/
    │       └── SKILL.md
    └── handoff/
        └── CURRENT.md
```

<div>
視需求再加入：

- `CONTEXT.md`：需要固定專有名詞時。
- `RUBRIC.md`：需要一致品質判準時。
- `docs/adr/`：需要保留難以逆轉的重要決策時。
- skill 的 `scripts/`、`references/`、`assets/`：流程確實需要時。

**先從一項會重複的工作開始，不必先建立完整文件宇宙。**
</div>
</split>


---

## 可直接修改的起始提示詞

### 請 Codex 協助規劃專案文件

```text
請使用 $writing-for-agents，先檢查這個研究資料夾與現有流程。
協助我規劃一份精簡的 AGENTS.md，以及它需要指向的專案文件。

請涵蓋：
1. 每次工作開始前應讀取的資料；
2. 資料、權限與修改範圍；
3. 可檢查的完成條件；
4. 完成後如何更新交接狀態。

詳細知識保留在單一權威文件，AGENTS.md 只放必要規則與清楚的讀取條件。
```

---

## 延伸到其他 Agent：共通知識＋平台入口

```text
共同專案文件（單一權威來源）
├── PROJECT.md
├── CONTEXT.md
├── RUBRIC.md
└── CURRENT.md
        ↓
平台專用的簡短入口
├── Codex       → AGENTS.md
├── 其他 Agent  → 該平台支援的指引檔
└── 共用 skill  → 各平台可讀取的相容格式
```

原則：

- 共通事實與決策只維護一份。
- 平台入口只說明何時讀取哪些共通文件。
- 若不同 Agent 的能力或格式不同，保留薄薄的轉接層。
- 每個平台都要實際測試：能否找到文件、遵守規則並完成驗證。

**跨 Agent 的目標不是讓所有設定完全相同，而是讓它們依同一份專案事實工作。**

---

## 參考資料

### Codex 官方文件

- [Custom instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Build skills](https://learn.chatgpt.com/docs/build-skills)

### Skills 生態系與本次推薦

- [skills.sh｜The Agent Skills Directory](https://www.skills.sh/)
- [find-skills](https://www.skills.sh/vercel-labs/skills/find-skills)
- [grill-me](https://www.skills.sh/mattpocock/skills/grill-me)
- [grill-with-docs](https://www.skills.sh/mattpocock/skills/grill-with-docs)
- [domain-modeling](https://www.skills.sh/mattpocock/skills/domain-modeling)

### 本次實例

- GKCSAF 專案根目錄的 `AGENTS.md`、`PROJECT.md`、`CONTEXT.md`、`RUBRIC.md`
- `.agents/handoff/CURRENT.md`
- `.agents/skills/` 下的四個專案專用 skills

> 本簡報只使用不含參與者識別資訊與個案逐字引文的專案結構及規則片段。