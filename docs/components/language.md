# Language 選擇語系選單

?>相關 css：scss/components/`_language.scss`
有文字版或是按鈕版，只需要放在不同的 div 中會自動切換  
文字版放置在`navList`
按鈕版放置在`subNavList`

**範例**

<nav class="topNav" role="navigation" aria-label="頁首功能列">
  <div class="navList">
    <div class="language sliderFn">
      <button type="button">語言選擇</button>
                  <ul id="languageList">
                    <li><a href="#">繁體中文</a></li>
                    <li><a href="#">简体中文</a></li>
                    <li><a href="#">ENGLISH</a></li>
                  </ul>
    </div>
  </div>
  <div class="subNavList">
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
<div class="language sliderFn">
  <button type="button">語言選擇</button>
  <ul id="languageList">
    <li><a href="#">繁體中文</a></li>
    <li><a href="#">简体中文</a></li>
    <li><a href="#">ENGLISH</a></li>
  </ul>
</div>
```

#### **JS/JQ**

```javascript
// 文字版
_toggleDropdown('.navList .language > button', '.navList .language ul'); //語系開關切換
// 按鈕版
_toggleDropdown('.subNavList .language > button', '.subNavList .language ul'); //語系開關切換
```

<!-- tabs:end -->

<script>
  _toggleDropdown('.navList .language > button', '.navList .language ul'); //語系開關切換
  _toggleDropdown('.subNavList .language > button', '.subNavList .language ul'); //語系開關切換
</script>
