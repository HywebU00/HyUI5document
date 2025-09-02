# SideNav 側邊選單

?>相關 css：scss/components/`_sideNav.scss`

只要在`mainBox`中增加`sideNav`的 aside，`main .container`會加上`display:flex;`的相關 css 設定。
側邊選單預設放置於畫面左方，`sideNavBtn`按鈕用於打開收合左側選單。  
側邊選單可以在`customize.js`中設定選項

<!-- tabs:start -->

#### **HTML**

```html
<aside class="sideNav" data-next-open="開啟下層選單" data-next-close="收合下層選單">
  <button type="button" id="sideNavBtn">次選單開關</button>
  <nav id="sideMenu" aria-label="側選單" role="navigation">
    <div class="sideMenuContent">
      <div class="sideTitle">側選單標題</div>
      <div class="sideNavBox">
        <ul>
          <li>
            <a href="#">
              <i class="icon"><img src="images/basic/icon/language_dk.svg" alt /></i>第一層選單1
            </a>
            <ul>
              <li>
                <a href="#">第二層選單1</a>
                <ul>
                  <li>
                    <a href="#">第三層選單1</a>
                  </li>
                  <li>
                    <a href="#">第三層選單2</a>
                  </li>
                </ul>
              </li>
              <li>
                <a href="#">第二層選單2</a>
              </li>
            </ul>
          </li>
          <li>
            <a href="#">
              <i class="icon"><img src="images/basic/icon/language_dk.svg" alt /></i>第一層選單2
            </a>
            <ul>
              <li>
                <a href="#">第二層選單1</a>
                <ul>
                  <li>
                    <a href="#">第三層選單1</a>
                  </li>
                  <li>
                    <a href="#">第三層選單2</a>
                  </li>
                </ul>
              </li>
              <li>
                <a href="#">第二層選單2</a>
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</aside>
```

#### **JS/JQ**

```javascript
sideNav({
  needLink: true, // 如果同時需要連結和下層功能時(手機版選單)
  floatType: true, // 切換是否由左側展開或是下方展開
  showDefault: true, // 是否預設顯示
});
```

- needLink 如果同時需要連結和下層功能時(手機版選單)，若設定`true`則點選箭頭才會展開下層，點選文字會是`a`連結。
- floatType 切換是否由左側展開或是下方展開。
- showDefault 設定一開始是否就展開側邊選單。
<!-- tabs:end -->

<style>
  .sideNav ul{
    padding-left:0px !important;
  }
</style>
<script>
sideNav({
  needLink: false, // 如果同時需要連結和下層功能時
});
</script>
