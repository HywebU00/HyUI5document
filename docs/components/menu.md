# Menu 主選單

?>相關 css：scss/components/`_menu.scss`

**主選單標籤**
為`mainMenu`及([範例](https://hywebu00.github.io/HyUI5/mp.html))，mainMenu 為判斷使用必須保留。

主選單在手機版預設放置於畫面左方`sidebar`，`mobileMainMenuBtn`按鈕用於打開收合左側選單。

主選單可以在`customize.js`中設定是否要`置頂`和是否為`megamenu`以及`手機版選單是否要外連和展開`同時可用。

<!-- **範例**

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
</div> -->

<!-- tabs:start -->

#### **HTML**

```html
<!-- 手機版主選單按鈕 Start -->
<button id="mobileMainMenuBtn" type="button">主選單</button>
<!-- 手機版主選單按鈕 End -->

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
```

#### **JS/JQ**

```javascript
mainMenu({
  sticky: true, // 是否置頂
  mega: false, // 是否megaMenu
  needLink: false, // 如果同時需要連結和下層功能時(手機版選單)
});
```

<!-- tabs:end -->

<style>
  .mainMenu{
    position:relative;
    z-index:5;
    display:block !important;
  }
  #mobileMenu{
    opacity: 1 !important;
    display: block !important;
    transform: translateX(0px) !important;
    position:relative !important;
  }
</style>
