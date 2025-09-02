# Search 搜尋

?>相關 css：相關 css：scss/components/`_search.scss`

網頁搜尋區塊預設是需要點選按鈕後才會展開搜尋區塊，若需要直接顯示搜尋區塊，只需要把`topNav`中`topSearch 按鈕`元件移除即會直接顯示。

**範例**

<header style="position:relative;">
<nav class="topNav" role="navigation" aria-label="頁首功能列">
  <div class="subNavList">
<div class="topSearch sliderFn">
  <button id="topSearchBtn" type="button">網站搜尋</button>
</div></div>
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
</header>

<!-- tabs:start -->

#### **HTML**

```html
<nav class="topNav" role="navigation" aria-label="頁首功能列">
  <div class="subNavList">
    <!-- topSearch 按鈕 Start -->
    <div class="topSearch sliderFn">
      <button id="topSearchBtn" type="button">網站搜尋</button>
    </div>
    <!-- topSearch 按鈕 ENd -->
  </div>
</nav>

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
```

<!-- tabs:end -->

<style>
  header{
    max-width:415px;
  }
.topNav{
justify-content: flex-start !important;
}
</style>
