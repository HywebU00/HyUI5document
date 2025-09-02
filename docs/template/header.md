# Header 頁首

?>相關 css：scss/template/`_header.scss`<br>

**頁首**由 **header** 標籤包覆，目前已預先設定 **h1 (logo 圖檔)** 、**navigation** 、 **search** 、 **menu** 等元素。

**內含預設模組可參考**

- [Navigation 導覽列](components/topnav.md)
- [Menu 主選單](components/menu.md)

以下模組依照無障礙 `tab`遊走順序擺放，如無特殊需求，皆依照由上到下、由左到右之順序呈現。

頁首模組皆已設定響應式風格樣式，目前斷點預設為 `991px` ，如需要更改斷點，請至`main.js`更改斷點變數，以及`_valuable.scss`更改斷點變數。

HyUI5 更新將 header 拆成`headTop`和`mainMenu`區塊，方便背景延伸設計處理。

**範例**

<header>
  <a class="accessKeyItem" href="#aU" id="aU" accesskey="U" aria-label="功能區塊">:::</a>
<div class="headTop">
<div class="container">
<!-- 手機版主選單按鈕 Start -->
<button id="mobileMainMenuBtn" type="button">主選單</button>
<!-- 手機版主選單按鈕 End -->
<!-- 網站標題 Start -->
<h1>
<a href="index.html"><img src="https://hywebu00.github.io/HyUI_5/images/footer_logo.png" alt="網站標題" />HyUI<span>Kit5</span></a>
</h1>
<!-- 網站標題 End -->
<!-- navigation Start -->
<nav class="topNav" role="navigation" aria-label="頁首功能列">
<!-- navList Start -->
<div class="navList">
<ul>
<li><a href="#">回首頁</a></li>
<li><a href="#">網站導覽</a></li>
<li><a href="#">常見問答</a></li>
</ul>
</div>
<!-- navList End -->
<!-- subNavList Start -->
<div class="subNavList">
<!-- fontSize Start -->
<div class="fontSize sliderFn">
<button type="button">文字大小</button>
<ul>
<li><button type="button" class="smallSize">小</button></li>
<li><button type="button" class="mediumSize">中</button></li>
<li><button type="button" class="largeSize">大</button></li>
</ul>
</div>
<!-- fontSize End -->
<!-- language Start -->
<div class="language sliderFn">
<button type="button">語言選擇</button>
<ul id="languageList">
<li><a href="#">繁體中文</a></li>
<li><a href="#">简体中文</a></li>
<li><a href="#">ENGLISH</a></li>
</ul>
</div>
<!-- language End -->
<!-- topSearch 按鈕 Start -->
<div class="topSearch sliderFn">
<button id="topSearchBtn" type="button">網站搜尋</button>
</div>
<!-- topSearch 按鈕 End -->
</div>
<!-- subNavList End -->
</nav>
<!-- navigation End -->
<!-- topSearch 手機版按鈕 Start -->
<button id="mobileSearchBtn" type="button" aria-label="搜尋按鈕"></button>
<!-- topSearch 手機版按鈕 End -->
<!-- topSearch 內容 Start -->
<div class="webSearch" role="search">
<div class="webSearchContent">
<div class="formList">
<label for="topSearchInput" class="srOnly">搜尋</label>
<input name="topSearchInput" id="topSearchInput" type="text" placeholder="請輸入文字" accesskey="S" aria-label="搜尋網站內容" />
<button type="button" class="btnPrimary">查詢</button>
<button type="button">進階搜尋</button>
</div>
<div class="hotKeyword">
<ul>
<li><a href="#">熱門熱門</a></li>
<li><a href="#">查詢</a></li>
<li><a href="#">字詞三</a></li>
</ul>
</div>
</div>
</div>
<!-- topSearch 內容 End -->
</div>
</div>
<!-- noscript -->
<noscript>
您的瀏覽器不支援 JavaScript 語法，JavaScript 語法並不影響內容的陳述。您可使用按鍵盤上的 Ctrl 鍵+ (+)鍵放大/(-)鍵縮小來改變字型大小；回到上一頁可使用瀏覽器提供的 Alt+左方向鍵(←) 快速鍵功能；列印可使用瀏覽器提供的(Ctrl+P)功能。您的瀏覽器，不支援 script 語法，若您的瀏覽器無法支援請點選此超連結
<a href="#">網站導覽</a>
</noscript>
<!-- menu Start -->
<div class="mainMenu">
<div class="container">
<nav class="menu" role="navigation" aria-label="主選單">
<ul>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li><a href="http://www.google.com">第一層有連結</a></li>
<li>
<a href="http://www.google.com">第一層有連結</a>
<ul>
<li><a href="http://www.google.com">第二層有連結</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li>
<a href="http://www.google.com">第二層有連結</a>
<ul>
<li>
<a href="http://www.google.com">第三層選單有下層</a>
<ul>
<li><a href="#">第四層選單</a></li>
<li><a href="#">第四層選單</a></li>
</ul>
</li>
<li>
<a href="http://www.google.com">第三層選單有連結</a>
</li>
<li><a href="#">第三層選單</a></li>
</ul>
</li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li>
<a href="#">第二層選單</a>
<ul>
<li><a href="#">第三層選單</a></li>
<li>
<a href="#">第三層選單</a>
<ul>
<li>
<a href="http://www.google.com">第四層選單有下層</a>
<ul>
<li><a href="#">第五層選單</a></li>
<li><a href="#">第五層選單</a></li>
</ul>
</li>
<li>
<a href="http://www.google.com">第四層選單有連結</a>
</li>
<li><a href="#">第四層選單</a></li>
</ul>
</li>
<li><a href="#">第三層選單</a></li>
<li><a href="#">第三層選單</a></li>
</ul>
</li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li>
<a href="#">第二層選單</a>
<ul>
<li>
<a href="http://www.google.com">第三層選單有下層</a>
<ul>
<li><a href="#">第四層選單</a></li>
<li><a href="#">第四層選單</a></li>
</ul>
</li>
<li>
<a href="http://www.google.com">第三層選單有連結</a>
</li>
<li><a href="#">第三層選單</a></li>
</ul>
</li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
</ul>
</nav>
</div>
</div>
<!-- menu End -->
</header>

<!-- tabs:start -->

#### **HTML**

```html
<!-- header Start -->
<header>
  <div class="headTop">
    <div class="container">
      <!-- 手機版主選單按鈕 Start -->
      <button id="mobileMainMenuBtn" type="button">主選單</button>
      <!-- 手機版主選單按鈕 End -->
      <!-- 網站標題 Start -->
      <h1>
        <a href="index.html"><img src="images/footer_logo.png" alt="網站標題" />HyUI<span>Kit5</span></a>
      </h1>
      <!-- 網站標題 End -->
      <!-- navigation Start -->
      <nav class="topNav" role="navigation" aria-label="頁首功能列">
        <a class="accessKeyItem" href="#aU" id="aU" accesskey="U" aria-label="功能區塊">:::</a>
        <!-- navList Start -->
        <div class="navList">
          <ul>
            <li><a href="#">回首頁</a></li>
            <li><a href="#">網站導覽</a></li>
            <li><a href="#">常見問答</a></li>
          </ul>
        </div>
        <!-- navList End -->
        <!-- submenuBox Start -->
        <div class="submenuBox">
          <!-- fontSize Start -->
          <div class="fontSize sliderFn">
            <button type="button">文字大小</button>
            <ul>
              <li><button type="button" class="smallSize">小</button></li>
              <li><button type="button" class="mediumSize">中</button></li>
              <li><button type="button" class="largeSize">大</button></li>
            </ul>
          </div>
          <!-- fontSize End -->
          <!-- language Start -->
          <div class="language sliderFn">
            <button type="button">語言選擇</button>
            <ul id="languageList">
              <li><a href="#">繁體中文</a></li>
              <li><a href="#">简体中文</a></li>
              <li><a href="#">ENGLISH</a></li>
            </ul>
          </div>
          <!-- language End -->
          <!-- topSearch 按鈕 Start -->
          <div class="topSearch sliderFn">
            <button id="topSearchBtn" type="button">網站搜尋</button>
          </div>
          <!-- topSearch 按鈕 End -->
        </div>
        <!-- submenuBox End -->
      </nav>
      <!-- navigation End -->
      <!-- topSearch 手機版按鈕 Start -->
      <button id="mobileSearchBtn" type="button" aria-label="搜尋按鈕"></button>
      <!-- topSearch 手機版按鈕 End -->
      <!-- topSearch 內容 Start -->
      <div class="webSearch" role="search">
        <div class="webSearchContent">
          <div class="formList">
            <label for="topSearchInput" class="srOnly">搜尋</label>
            <input name="topSearchInput" id="topSearchInput" type="text" placeholder="請輸入文字" accesskey="S" aria-label="搜尋網站內容" />
            <button type="button" class="btnPrimary">查詢</button>
            <button type="button">進階搜尋</button>
          </div>
          <div class="hotKeyword">
            <ul>
              <li><a href="#">熱門熱門</a></li>
              <li><a href="#">查詢</a></li>
              <li><a href="#">字詞三</a></li>
            </ul>
          </div>
        </div>
      </div>
      <!-- topSearch 內容 End -->
    </div>
  </div>
  <!-- noscript -->
  <noscript>
    您的瀏覽器不支援JavaScript語法，JavaScript語法並不影響內容的陳述。您可使用按鍵盤上的Ctrl鍵+ (+)鍵放大/(-)鍵縮小來改變字型大小；回到上一頁可使用瀏覽器提供的 Alt+左方向鍵(←) 快速鍵功能；列印可使用瀏覽器提供的(Ctrl+P)功能。您的瀏覽器，不支援script語法，若您的瀏覽器無法支援請點選此超連結
    <a href="#">網站導覽</a>
  </noscript>
  <!-- menu Start -->
  <div class="mainMenu">
    <div class="container">
      <nav class="menu" role="navigation" aria-label="主選單">
        <ul>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li><a href="http://www.google.com">第一層有連結</a></li>
          <li>
            <a href="http://www.google.com">第一層有連結</a>
            <ul>
              <li><a href="http://www.google.com">第二層有連結</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li>
                <a href="http://www.google.com">第二層有連結</a>
                <ul>
                  <li>
                    <a href="http://www.google.com">第三層選單有下層</a>
                    <ul>
                      <li><a href="#">第四層選單</a></li>
                      <li><a href="#">第四層選單</a></li>
                    </ul>
                  </li>
                  <li>
                    <a href="http://www.google.com">第三層選單有連結</a>
                  </li>
                  <li><a href="#">第三層選單</a></li>
                </ul>
              </li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li>
                <a href="#">第二層選單</a>
                <ul>
                  <li><a href="#">第三層選單</a></li>
                  <li>
                    <a href="#">第三層選單</a>
                    <ul>
                      <li>
                        <a href="http://www.google.com">第四層選單有下層</a>
                        <ul>
                          <li><a href="#">第五層選單</a></li>
                          <li><a href="#">第五層選單</a></li>
                        </ul>
                      </li>
                      <li>
                        <a href="http://www.google.com">第四層選單有連結</a>
                      </li>
                      <li><a href="#">第四層選單</a></li>
                    </ul>
                  </li>
                  <li><a href="#">第三層選單</a></li>
                  <li><a href="#">第三層選單</a></li>
                </ul>
              </li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li>
                <a href="#">第二層選單</a>
                <ul>
                  <li>
                    <a href="http://www.google.com">第三層選單有下層</a>
                    <ul>
                      <li><a href="#">第四層選單</a></li>
                      <li><a href="#">第四層選單</a></li>
                    </ul>
                  </li>
                  <li>
                    <a href="http://www.google.com">第三層選單有連結</a>
                  </li>
                  <li><a href="#">第三層選單</a></li>
                </ul>
              </li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
        </ul>
      </nav>
    </div>
  </div>
  <!-- menu End -->
</header>
```

<!-- tabs:end -->

<script>
  _toggleDropdown('.subNavList .fontSize > button', '.subNavList .fontSize ul'); //文字大小展開開關切換
  _toggleDropdown('.navList .fontSize > button', '.navList .fontSize ul'); //文字大小展開開關切換
  _toggleDropdown('header .subNavList .language > button', 'header .subNavList .language ul'); //語系開關切換
  _toggleDropdown('header .navList .language > button', 'header .navList .language ul'); //語系開關切換
  mainMenu({
  sticky: true, // 是否置頂
  mega: false, // 是否megaMenu
  needLink: false, // 如果同時需要連結和下層功能時(手機版選單)
});
</script>
