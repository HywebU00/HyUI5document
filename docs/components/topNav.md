# Navigation 導覽列

?>相關 css：scss/components/`_topNav.scss`

Navigation 分為兩個區塊，一個是左方只有文字部分`navList`，另外一個是右方有按鈕的部分`subNavList`。

**內含預設模組可參考**

- [fontSize 字型大小](components/fontsize.md)
- [language 語系](components/language.md)
- [Search 搜尋](components/search.md)

**範例**

<header style="position:relative">
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
  <!-- submenuBox Start -->
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
  <!-- submenuBox End -->
</nav>

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
</div></header>

<!-- tabs:start -->

#### **HTML**

```html
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
<!-- navigation End -->
```

#### **JS/JQ**

```javascript
_toggleDropdown('.subNavList .language > button', '.subNavList .language ul'); //語系開關切換
_toggleDropdown('.subNavList .fontSize > button', '.subNavList .fontSize ul'); //文字大小展開開關切換
```

<!-- tabs:end -->

<h2>其他用法</h2>

以目前預設功能希望**右邊按鈕移動到左邊文字區**可以將元件拉進`navList`區塊即可。

**範例**

<nav class="topNav" role="navigation" aria-label="頁首功能列">
  <div class="navList">
    <ul>
      <li><a href="#">回首頁</a></li>
      <li><a href="#">網站導覽</a></li>
      <li><a href="#">常見問答</a></li>
    </ul>
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
    <div class="language sliderFn">
      <button type="button">語言選擇</button>
      <ul id="languageList">
        <li><a href="#">繁體中文</a></li>
        <li><a href="#">简体中文</a></li>
        <li><a href="#">ENGLISH</a></li>
      </ul>
    </div>
  </div>
</nav>

<!-- tabs:start -->

#### **HTML**

```html
<div class="navList">
  <ul>
    <li><a href="#">回首頁</a></li>
    <li><a href="#">網站導覽</a></li>
    <li><a href="#">常見問答</a></li>
  </ul>

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
</div>
```

#### **JS/JQ**

```javascript
_toggleDropdown('.navList .language > button', '.navList .language ul'); //語系開關切換
_toggleDropdown('.navList .fontSize > button', '.navList .fontSize ul'); //文字大小展開開關切換
```

<!-- tabs:end -->

<style>
  header{
    max-width:420px;
  }
.topNav{
justify-content: flex-start !important;
}
</style>
<script>
  _toggleDropdown('.subNavList .language > button', '.subNavList .language ul'); //語系開關切換
  _toggleDropdown('.subNavList .fontSize > button', '.subNavList .fontSize ul'); //文字大小展開開關切換
_toggleDropdown('.navList .language > button', '.navList .language ul'); //語系開關切換
_toggleDropdown('.navList .fontSize > button', '.navList .fontSize ul'); //文字大小展開開關切換
</script>
