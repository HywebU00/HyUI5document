## HTML 範本

hyUI5

```html
<!DOCTYPE html>
<html lang="zh-Hant" class="no-js">
  <head>
    <!-- 使用 noindex 禁止 Google 搜尋建立索引，套版時請工程師刪掉這行 -->
    <meta name="robots" content="noindex" />
    <!-- 使用 noindex 禁止 Google 搜尋建立索引，套版時請工程師刪掉這行 -->
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>HyUI kit</title>
    <!-- style css -->
    <link rel="stylesheet" href="css/style.css" />
    <!-- 其他色系 css -->
    <link rel="stylesheet" href="css/blue.css" />
    <!-- favicon -->
    <link href="images/favicon.png" rel="icon" type="image/x-icon" />
  </head>
  <body>
    <!-- wrapper Start -->
    <div class="wrapper">
      <!-- 直接跳主內容區 -->
      <a class="goCenter" href="#aC">按Enter到主內容區</a>

      <!-- header Start -->
      <header>
        <!-- 內容區塊 Start -->
        <div class="headTop">
          <div class="container">
            <!-- 手機版主選單按鈕 Start -->
            <button id="mobileMainMenuBtn" type="button">主選單</button>
            <!-- 手機版主選單按鈕 End -->
            <!-- 網站標題 Start -->
            <h1>
              <a href="index.html"><img src="images/footer_logo.png" alt />HyUI<span>Kit5</span></a>
            </h1>
            <!-- 網站標題 End -->
            <!-- navigation Start -->
            <nav class="topNav" role="navigation" aria-label="頁首功能列">
              <a class="accessKeyItem" href="#aU" id="aU" accesskey="U" aria-label="功能區塊">:::</a>
            </nav>
            <!-- navigation End -->
            <!-- topSearch 手機版按鈕 Start -->
            <button id="mobileSearchBtn" type="button" aria-label="搜尋按鈕"></button>
            <!-- topSearch 手機版按鈕 End -->
          </div>
        </div>
        <!-- noscript Start -->
        <noscript>
          您的瀏覽器不支援JavaScript語法，JavaScript語法並不影響內容的陳述。您可使用按鍵盤上的Ctrl鍵+ (+)鍵放大/(-)鍵縮小來改變字型大小；回到上一頁可使用瀏覽器提供的 Alt+左方向鍵(←) 快速鍵功能；列印可使用瀏覽器提供的(Ctrl+P)功能。您的瀏覽器，不支援script語法，若您的瀏覽器無法支援請點選此超連結
          <a href="#">網站導覽</a>
        </noscript>
        <!-- noscript End -->
        <!-- menu Start -->
        <div class="mainMenu">
          <div class="container">
            <nav class="menu" role="navigation" aria-label="主選單">
              <ul>
                <li>
                  <a href="#">第一層選單</a>
                  <ul>
                    <li>
                      <a href="#">第二層選單</a>
                      <ul>
                        <li>
                          <a href="#">第三層選單</a>
                        </li>
                      </ul>
                    </li>
                  </ul>
                </li>
              </ul>
            </nav>
          </div>
        </div>
        <!-- menu End -->
        <!-- 內容區塊 End -->
      </header>
      <!-- header End -->

      <!-- main Start -->
      <main>
        <a class="accessKeyItem" href="#aC" id="aC" accesskey="C" aria-label="主要內容區">:::</a>
        <div class="container">
          <!-- 內容區塊 Start -->
          <div class="mainContentBox"></div>
          <!-- 內容區塊 End -->
          ...
        </div>
      </main>
      <!-- main End -->

      <!-- footer Start-->
      <footer>
        <a class="accessKeyItem" href="#aZ" id="aZ" accesskey="Z" aria-label="頁尾區">:::</a>
        <!-- 內容區塊 Start -->
        <div class="container"></div>
        <!-- 內容區塊 End -->
      </footer>
      <!-- footer End-->
    </div>
    <!-- wrapper End -->
    <!-- 回到頂部 Start -->
    <button id="scrollTop" type="button" aria-label="回到頂部">TOP</button>
    <!-- 回到頂部 End -->

    <!-- fancyBox -->
    <script src="assets/fancybox/fancybox.umd.js"></script>
    <script src="assets/fancybox/l10n/zh_TW.umd.js"></script>
    <!-- Swiper -->
    <script src="assets/swiper/swiper-bundle.min.js"></script>
    <!-- js -->
    <script src="js/main.js"></script>
    <script src="js/customize.js"></script>
  </body>
</html>
```

---

## 設定網頁的語系

設定網頁的語系 讓瀏覽器能更正確解析與編碼

```html
<!DOCTYPE html>
<html lang="zh-Hant" class="no-js"></html>
```

**HTML** 的 `lang` 屬性可用於網頁或部分網頁的語言。這對搜索引擎和瀏覽器是有幫助的。 根據 **W3C** 推薦標準，應該通過 `<html>`標籤中的 `<lang>`屬性對每張頁面中的主要語言進行聲明。相關資料請參考 [W3C Language Codes](https://www.w3schools.com/tags/ref_language_codes.asp)。

| 常見語系                       | 對應設定       |
| :----------------------------- | :------------- |
| English                        | lang='en'      |
| 繁體中文 Chinese (Traditional) | lang='zh-Hant' |
| 簡體中文 Chinese (Simplified)  | lang="zh-CN"   |

!>為了無障礙於關閉 Javascript 的檢測，請先預留此`class="no-js"` 的設定。更多內容請參考[無障礙單元](quick-start/print.md)。

---

## head 內容

```html
<meta charset="utf-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>HyUI kit</title>
<!-- hyUI css -->
<link rel="stylesheet" href="css/style.css" />
<!-- 其他顏色 -->
<link rel="stylesheet" href="css/blue.css" />
<!-- favicon -->
<link href="images/favicon.png" rel="icon" type="image/x-icon" />
```

`<meta http-equiv="X-UA-Compatible" content="IE=edge">` 預設指定 **IE 瀏覽器** 按照最高的標準模式解析頁面。

`<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">`預設畫面載入初始縮放比例 100%。

`shrink-to-fit=no`這個屬性為 **iOS 9** 能新辨認的屬性：**shrink-to-fit** 並設定為 **no**，這設定可以讓網頁的寬度自動適應手機螢幕的寬度。

以下兩種設定都可以防止使用者做畫面縮放，將畫面鎖在縮放比例 100%

```html
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1" />
```

```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
```

### 載入 CSS

範本已先預設匯入`style.css`、`blue.css`

```html
<link rel="stylesheet" href="css/style.css" />
<!-- 其他顏色 -->
<link rel="stylesheet" href="css/blue.css" />
```

---

## 網站內容

除放置網站主要內容`main`和`footer`以外會另外放置以下內容。

### 回頁首按鈕

`<body>`預設已存在 "回頁首"的按鈕，可自行調整內容，但需保留 `id`。

```html
<button id="scrollTop" type="button" aria-label="回到頂部">TOP</button>
```

---

### JavaScript

範本已先預設匯入下列 **JavaScript** 檔案，可根據需求增減刪除。

```html
<!-- fancyBox -->
<script src="assets/fancybox/fancybox.umd.js"></script>
<script src="assets/fancybox/l10n/zh_TW.umd.js"></script>
<!-- Swiper -->
<script src="assets/swiper/swiper-bundle.min.js"></script>
<!-- js -->
<script src="js/main.js"></script>
<script src="js/customize.js"></script>
```

#### FancyBox

知名的燈箱套件，使用需購買使用憑證。

```html
<script src="vendor/fancybox/fancybox.umd.js"></script>
<script src="vendor/fancybox/l10n/zh_TW.umd.js"></script>
```

須在`scss/style.scss`中加載 css 檔案，已預設加載。

```css
@import '../vendor/fancybox/fancybox.css';
```

#### swiper

Swiper 常用於行動端網站的內容觸控滑動，是純 javascript 打造的滑動特效插件，面向手機、平板電腦等行動終端。  
Swiper 能實現觸控螢幕焦點圖、觸控螢幕 Tab 切換、觸控螢幕輪播圖切換等常用效果。

```html
<script src="vendor/swiper/swiper-bundle.min.js"></script>
```

須在`scss/style.scss`中加載 css 檔案，已預設加載。

```css
@import '../vendor/swiper/swiper-bundle.min.css';
```

#### main.js

預設提供常用之**互動模組**，使用 javascript 撰寫。如果沒有特殊的版本更新需求，請不任意新增或刪除 `main.js` 的預設設定。  
另外還有 JQuery 版本 `mainJq.js` 全由 JQuery 撰寫。

<!-- tabs:start -->

### **js**

```html
<script src="js/main.js"></script>
```

### **jq**

```html
<script src="vendor/jquery-3.7.1.min.js"></script>
<script src="js/mainJq.js"></script>
```

<!-- tabs:end -->

#### customize.js

可自行撰寫所需要的互動程式，可寫在 `customize.js`
當禁用 JavaScript 時，請視情況於網頁顯示`<noscript>`，並標記上相關說明文字。

```html
<script src="js/customize.js"></script>
```
