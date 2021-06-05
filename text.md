# 製作專案架構

## [後端架構](https://github.com/willy874/willy874.github.io/tree/master/app)

1. 採用 nodejs express
2. 使用後端主流的 router controller model service 來進行抽象分層
3. Router 具備基本的 Restful API 自動建立特性，依據 models 來自動產生相關需要的 API，並與 Controller 自動接耦與解耦，增加開發的便利性。 [link](https://github.com/willy874/willy874.github.io/tree/master/app/router)

## [自動化](https://github.com/willy874/willy874.github.io/tree/master/auto)

### [Model 建立工具](https://github.com/willy874/willy874.github.io/tree/master/auto/model)

因為各種 Model 的介面設定與擋案設定處理過於繁雜而重複，為了工作行為不要重工，只要建立一次設定檔，由 nodejs 產生 modeljs 檔案。設定檔也比在建構式時更易於閱讀。內部也有提供是否覆複寫的設定參數。

### [Rollup 套件打包](https://github.com/willy874/willy874.github.io/tree/master/auto/rollup-bundle)

一些共用函式與套件因為常常要複製貼上與搬運，所以使用 Rollup 來統一打包散亂的資料夾與檔案，便可以統一集中管理，未來會規話另拆出變 npm plugin 來安裝。

### [Migration 資料庫遷移](https://github.com/willy874/willy874.github.io/tree/master/auto/migration)

過去經常接處的是 PHP Laravel 的後端框架，希望使用接口與介面相似的架構，因此自行設計的 Migration 系統，以 MySQL 為對象直接對資料庫進行操作。

### [create-index 索引產生器](https://github.com/willy874/willy874.github.io/tree/master/auto/create-index)

在 ES6 中經常使用模塊開發，但為了方便引入經常要寫索引檔案，因此寫了一支自動產生索引的工具來為我工作。

### [SVG 轉換器](https://github.com/willy874/willy874.github.io/tree/master/auto/svg)

因為不喜歡直接使用 `img(src="...")` 方式引入 Icon，所以幾乎採用 JS 來掛載，但要把大量的 icon.svg 轉成 JS 檔案使用非常麻煩，因此建立該工具來產生自己需要的 JS 格式。

## [後台架構](https://github.com/willy874/willy874.github.io/tree/master/backend)

1. 採用 Model 管理資料，嚴格限制 JS 的型別問題，並產生預設值。以 OOP 的方式來管理各 Restful API 的資料狀態。
2. 管理者權限管理系統，管理登入登出與各路由間的權限。
3. 緩存資料庫，以 localStorage 作為長期記憶的前端料庫，在每次 PP 啟動時釋放資料，並在打完 API 之後同步緩存資料。

## [插件製作](https://github.com/willy874/willy874.github.io/tree/master/plugins)

### [便利函式](https://github.com/willy874/willy874.github.io/tree/master/plugins/function)

目前已製作命名轉換工具、非同步管理工具。

### [Dialog UI](https://github.com/willy874/willy874.github.io/tree/master/plugins/dialog)

自行搭建的 Dialog UI 插件，每次較回傳 Promise 來非同步管理視窗。具備多層視窗功能，並可以進行切換。視窗可以用滑鼠及觸控拖拉改變位置，並支援 RWD 的變化來改變定位與寬度。

### [Icon UI](https://github.com/willy874/willy874.github.io/tree/master/plugins/icon)

可以將 Icon 設定檔引入到內部，吐出可以直接 mount 在畫面上的組件。
