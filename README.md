# 靜態頁面開發環境（使用 Gulp ）
簡單的 Gulp 配置，可快速架設開發靜態網頁所需的環境。
## 本環境可以幫你做的事
本環境滿足之需求為以下 3 項：
1. SCSS / Sass 的編譯與完善
2. 檔案（CSS、JavaScript、HTML與圖片檔）的壓縮
3. 瀏覽器 LiveReload 即時呈現
## 專案結構
```
StaticPagesDevSet
    |
    └── src // 原始檔資料夾，在這裡編寫網頁
    |   └── img
    |   └── js
    |   └── scss
    |   └── index.html 
    |
    └── dist // 由 gulp 自動產生的發佈檔
    |   └── css
    |   └── img
    |   └── js  
    |
    └── node_modules
    |
    └── gulpfile.js
    |
    └── index.html
    |
    └── package.json
    |
    └── README.md
```
## 各個 gulp.task 說明
詳細配置請查看 gulpfile.js

### processSCSS

```javascript
gulp processSCSS
```

編譯  src/scss 裡的 .scss 檔案成 .css，同時加上前綴與最小化。  

最後存入 dist/css 。  
### processJS

```javascript
gulp processJS
```

利用 jshint 檢查 src/js 裡的 .js 檔案，然後進行醜化。

最後存入 dist/js 。

### proceeIMG

```javascript
gulp processIMG
```

壓縮 src/img 裡的圖片檔。

最後存入 dist/img 。

### processHTML

```javascript
gulp processHTML
```

壓縮 src/index.html。

最後存入根目錄。

### cleanDist 

```javascript
gulp cleanDist
```

刪除舊的 dist 資料夾，並免不必要的錯誤。

### watch 監視任務

```javascript
gulp watch
```
開啟 web server 後，監視 src 裡的原始檔，一有變化就執行處理程序並 reload 頁面。

### 預設任務
```javascript
gulp
```
執行任務如下:

   cleanDist  

-> (異步執行 processSCSS、processJS、processIMG、processHTML)  

-> watch 

## 使用
1. 安裝 Node.js，請參閱 [Node.js Downloads](https://nodejs.org/en/download/)
2. 安裝 Gulp，請參閱 [Gulp](http://gulpjs.com)
3. 複製下載本 Repo
```git
Clone git@github.com:sss63232/StaticPagesDevSet.git
```
4. 安裝 npm 套件
```javascript
npm install
```
5. 執行 gulp 任務
```javascript
gulp
```

