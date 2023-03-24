---
{"dg-publish":true,"permalink":"/R package/data/data.table/install data.table/","title":"如何在Mac M1上使用data.table多核運算","tags":["Rpackage/data","data.table","blog"],"created":"2023-03-23T00:00:00.000Z","updated":"2023-03-24T00:00:00.000Z"}
---


在mac M1上使用R的`data.table`，這個資料處理套件時先前都會發生偵測不到openMP的錯誤，導致無法多核運算。先前雖然根據`data.table`的[wiki](https://github.com/Rdatatable/data.table/wiki/Installation)安裝步驟試了幾次卻總是失敗。事隔多月，今天突然成功了。紀錄一下成功的安裝過程。

## 1. 安裝xcode

在terminal中執行以下

```
xcode-select --install
```

## 2. Install libomp

1. 先安裝[homebrew](https://brew.sh/)
2. 執行以下指令

```
brew update && brew install libomp
```

## 3. Update Makevars

1. 在finder當中按下`shift+cmd+.`開啟檢視隱藏檔
2. 在`使用者/使用者名稱/.R`當中建立`Makevars`這個檔案，若存在就修改內容即可
3. 在這個檔案內貼上以下內容

```
LDFLAGS += -L/opt/homebrew/opt/libomp/lib -lomp
CPPFLAGS += -I/opt/homebrew/opt/libomp/include -Xclang -fopenmp
```

## 4. 在R當中安裝data.table

執行`install.packages("data.table", type = "source")`

也許使用source安裝會是這次可以成功的關鍵？
