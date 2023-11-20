# Tailwind CSS 起手式

> [!WARNING]
> 在執行以下動作前，請先確認有沒有安裝Node.js


### ==STEP1==  初始 npm 專案
透過終端機指定資料夾位置後初始 npm 專案，並生成 packge.json 管理安裝模組
```
npm init -y  //-y等於--yes, 接受所有預設值並產生package.json，也就是建立專案時，全部按 yes
```


### ==STEP2== 安裝 Tailwind CSS

在資料夾中的終端機透過 npm 安裝\`tailwindcss\`

```
npm install -D tailwindcss autoprefixer

or

npm install tailwindcss@latest postcss@latest autoprefixer@latest

//autoprefixer會幫忙生成各家瀏覽器的前綴詞
```
安裝完畢後，建立\`tailwind.config.js\`
```
## tailwind.config.js ##

------------------------------------------------------- 

提供下列三種初始tailwindz方式，生成tailwind.config.js

<!-- 建立設定檔(這個就行) -->
$ npx tailwindcss init

<!-- 建立包含所有預設值的設定檔 -->
$ npx tailwindcss init --full

<!-- 建立設定檔與 postcss.config.js -->
$ npx tailwindcss init -p
```

> npm 和 npx的差異
> 
> npm指的是永久安裝，npx安裝後即移除

> #### 什麼時候要用 NPX ?
> 
> npm 會全局性的安裝 global-package ，這個 global-package (dependency) 也會一直存在本機 node_modules 下，如果使用 npx 命令， global-package 會被安裝在臨時安裝包上，等到項目初始化完成後就會刪除，不用全局性的安裝，避免被汙染。
> 
> 像是那種一次性使用的，如 creat-react-app 它只有用在建立專案的最一開始，之後就不會用了! 或是像 npkill 套件， 這個套件是會幫我們清理無效的 node_modules ，在大專案下可以五到六個月跑一次，這時候使用 NPX 就再好不過啦!
> 
> 詳細介紹可閱讀下列文章：https://medium.com/itsems-frontend/whats-npx-e83400efe7f8

### ==STEP3==  Configure your template paths / 配置模板路徑
```
/** @type {import('tailwindcss').Config} */

//告訴tailwind html檔在哪，src是可以更改的，如果會將html文件放在dist資料夾，那src要更改成dist

module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
### ==STEP4==  Add the Tailwind directives to your CSS / 新增 Tailwind 到 CSS 中
新增一個src資料夾並新增一個 \`input.css\` 檔案 (依照專案可自訂義此名字)
再把 Tailwind 的三個核心複製貼到剛剛新建的 CSS 檔案中。

```
/** input.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

/* 你可以在這裡自訂你的CSS樣式 */
```

### ==STEP5==  Start the Tailwind CLI build process
雖然官方強力推薦要搭配 PostCSS，但因為還要去了解 PostCSS 沒有那麼容易，所以為了達到比較無障礙的使用，就不依賴 PostCSS 來使用，可以輸入下方指令，就可以將 Tailwind 編譯成瀏覽器看得懂的 CSS，完成後就可以直接使用 Tailwind 了！
```
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```
或是在package.json加入下行
```
"scripts": {
    "build": "tailwindcss -i ./src/input.css -o ./dist/output.css --watch"
  },
```
需要編譯時再執行
```
npm run build
```
> ### 注意
> 編譯成功畫面如下，warn代表目前HTML中尚未使用 tailwind css 的 class，加入後警告就會消失
> ![](https://hackmd.io/_uploads/S1EpEtHJa.png)


### ==STEP6==  set gitignore / 設定 gitignore
新增一個檔案，命名為`.gitignore`，寫入`node_modules`讓 git 忽略上傳node_modules裡的檔案
```
## .gitignore ##
------------------------------------------------------- 
/node_modules
.DS_store (只針對macOS)
```

### ==FINAL==  Start using Tailwind in your HTML / 開始使用 Tailwind CSS
在HTML的\<head\> 標籤中加入`<link href="/dist/output.css" rel="stylesheet">`即可使用
```
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/dist/output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```

---

### ==客製化設定== Purge CSS 幫 CSS瘦身
Tailwind 因為是 Utility 的關係，會把整包檔案匯入，但我可能這次專案沒有用到這麼多的 Utility，如果整包檔案要選染於網頁，效能就會低落，Tailwind 官方文件很貼心也提供可以瘦身的方法，選到 tailwind.config.js 檔案，將我可能會使用到的內容寫在 purge 屬性內，就可以去監聽我哪支檔案有使用到，只會編譯使用的檔案，真的很貼心呢！
```
module.exports = {
  purge: {
    enabled: true,                //如需手動啟用加入這行
    content: [
        './**/*.html',            //加入路徑，設定清除對象
        './src/**/*.vue',
    ],
    preserveHtmlElements: false,  //清除HTML基本樣式(不建議)
    
  },
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
};
```
Tailwind CSS v3 之後請改寫如下：
由於 Tailwind 不再在後台使用 PurgeCSS，我們已將該選項重命名purge為content以更好地反映它的用途：
```
/** @type {import('tailwindcss').Config} */

module.exports = {
  content: [
    './components/**/*.{html,js}',
    './build/**/*.html', //告訴tailwind 我們的html檔在哪裡
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### ==客製化設定== Prettier 自動調整 TailwindCSS class 順序
```
npm install -D prettier prettier-plugin-tailwindcss
```
