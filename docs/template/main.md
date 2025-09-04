# Main 主要內容

?>相關 css：scss/template/`_main_.scss`

首頁跟內容頁的 class 會有些許不同。  
 若 class 裡有 full 代表滿版，會清除`container`的`max-width`和`padding`

**內含預設模組可參考**

- [fontSize 字型大小](components/fontsize.md)

<!-- tabs:start -->

#### **首頁 Html**

```html
<main class="main">
  <!-- 無障礙導盲磚 -->
  <a class="accessKeyItem" href="#aC" id="aC" accesskey="C" aria-label="主要內容區">:::</a>
  <div class="mainBox">
    <!-- 區塊 Start -->
    <section>
      <div class="container">
        <div class="flexTpl_12 full"></div>
      </div>
    </section>
    <!-- 區塊 End -->
  </div>
</main>
```

#### **內頁 Html**

內頁有區分有側邊欄位或是沒有側邊欄位

**沒有側邊欄位**

```html
<main class="innerPage">
  <!-- 無障礙導盲磚 -->
  <a class="accessKeyItem" href="#aC" id="aC" accesskey="C" aria-label="主要內容區">:::</a>
  <div class="container">
    <!-- 主內容區 Start -->
    <div class="mainContentBox">
      <h2 class="pageTitle">節點標題</h2>

      <div class="mainContent">
        <!-- 內容放置區塊 -->
      </div>
    </div>
    <!-- 主內容區 End -->
  </div>
</main>
```

**有側邊欄位**

在`container` 中增加 `aside` 相關 html， css 自動判斷有側邊欄位。

```html
<main class="innerPage">
  <a class="accessKeyItem" href="#aC" id="aC" accesskey="C" aria-label="主要內容區">:::</a>
  <div class="container">
    <!-- sideNav Start -->
    <aside class="sideNav">
      <button id="sideNavBtn" type="button">次選單開關</button>
      <nav id="sideMenu" aria-label="側選單">
        <div class="sideMenuContent">
          <div class="sideTitle">側選單標題</div>
          <div class="sideNavBox"></div>
        </div>
      </nav>
    </aside>
    <!-- sideNav End -->

    <!-- 主內容區 Start -->
    <div class="mainContentBox">
      <h2 class="pageTitle">節點標題</h2>
      <div class="mainContent">
        <!-- 內容放置區塊 -->
      </div>
    </div>
    <!-- 主內容區 End -->
  </div>
</main>
```

<!-- tabs:end -->
