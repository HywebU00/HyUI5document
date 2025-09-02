# FontSize 控制文章字體大小

?>相關 css：scss/components/`_fontSize.scss`  
相關 css：scss/components/`_functionPanel.scss` (內頁內容區)

> 使用 css zoom 功能，不再只是影響到字型，整個版型都會被調整，但還是會符合 RWD 效果，好處是可以針對區塊去各別設定大小，可於 `scss/basic/_default.scss`設定大小，預設為 `smallSize` 小尺寸 `1rem` 大小，為網站的基本設定。

- 小型字體大小：1(16px)
- 中型字體大小：1.125(18px)
- 大型字體大小：1.25(20px)

<!-- 文字大小 -->

### 全站共用

影響全站尺寸

**範例**

<div class="subNavList">
  <div class="fontSize sliderFn">
    <button type="button">文字大小</button>
    <ul>
      <li><button type="button" class="smallSize">小</button></li>
      <li><button type="button" class="mediumSize">中</button></li>
      <li><button type="button" class="largeSize">大</button></li>
    </ul>
  </div>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="subNavList">
  <div class="fontSize sliderFn">
    <button type="button">文字大小</button>
    <ul>
      <li><button type="button" class="smallSize">小</button></li>
      <li><button type="button" class="mediumSize">中</button></li>
      <li><button type="button" class="largeSize">大</button></li>
    </ul>
  </div>
</div>
```

#### **CSS**

```scss
body {
  &.mediumSize {
    zoom: 1.125;
  }

  &.largeSize {
    zoom: 1.25;
  }
}
```

#### **JS/JQ**

```javascript
_toggleDropdown('.subNavList .fontSize > button', '.subNavList .fontSize ul'); //文字大小展開開關切換
```

<!-- tabs:end -->

### 內頁區塊使用

只影響內容區塊部分

**範例**

<div class="functionPanel">
  <div class="fontSizeInner">
    <span>字型大小：</span>
    <ul>
      <li><button type="button" class="smallSize">小</button></li>
      <li><button type="button" class="mediumSize">中</button></li>
      <li><button type="button" class="largeSize">大</button></li>
    </ul>
  </div>
  </div>

<div class="mainContentBox">
<div class="mainContent">
Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quam excepturi tempore, enim unde modi error ea est omnis facilis nisi odio alias quod doloremque ipsam illo sint sapiente. Sit, libero.</div>
</div>
<!-- tabs:start -->

#### **HTML**

```html
<div class="fontSizeInner">
  <span>字型大小：</span>
  <ul>
    <li><button type="button" class="smallSize">小</button></li>
    <li><button type="button" class="mediumSize">中</button></li>
    <li><button type="button" class="largeSize">大</button></li>
  </ul>
</div>
```

#### **CSS**

```scss
.mainContent {
  &.mediumSize {
    zoom: 1.125;
  }

  &.largeSize {
    zoom: 1.25;
  }
}
```

<!-- tabs:end -->

<style>
  .functionPanel{
    justify-content: flex-start !important;
  }
</style>
<script>
  _toggleDropdown('.subNavList .fontSize > button', '.subNavList .fontSize ul'); //文字大小展開開關切換
</script>
