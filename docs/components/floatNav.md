# floatNav 固定側邊欄

?>相關 css：scss/components/`_floatNav.scss`

HyUI 提供固定`側邊欄`的作法，固定特定位置，而不隨滾動欄滾動。

<!-- panels:start -->
<!-- div:left-panel -->

**typeA**

<div class="demo">
<div class="floatNav">
  <ul class="typeA">
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/facebook.svg" alt="facebook" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/youtube.svg" alt="youtube" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/x.svg" alt="x" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/instagram.svg" alt="instagram" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/email.svg" alt="email" /></a>
    </li>
  </ul>
</div>
</div>

<!-- div:right-panel -->

**typeB**

<div class="demo">
<div class="floatNav">
  <ul class="typeB">
    <li>
      <a href="#">
        <div class="pic"><i class="i_account_circle_w"></i></div>
        <div class="listTitle">側邊第一選項</div>
      </a>
    </li>
    <li>
      <a href="#">
        <div class="pic"><i class="i_account_circle_w"></i></div>
        <div class="listTitle">側邊第二選項</div>
      </a>
    </li>
    <li>
      <a href="#">
        <div class="pic"><i class="i_account_circle_w"></i></div>
        <div class="listTitle">側邊第三選項</div>
      </a>
    </li>
    <li>
      <a href="#">
        <div class="pic"><i class="i_account_circle_w"></i></div>
        <div class="listTitle">側邊第四選項</div>
      </a>
    </li>
  </ul>
</div>
</div>

<!-- panels:end -->
<!-- tabs:start -->

#### **typeA Html**

```html
<div class="floatNav">
  <ul class="typeA">
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/facebook.svg" alt="facebook" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/youtube.svg" alt="youtube" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/x.svg" alt="x" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/instagram.svg" alt="instagram" /></a>
    </li>
    <li>
      <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/email.svg" alt="email" /></a>
    </li>
  </ul>
</div>
```

#### **typeB Html**

```html
<div class="floatNav">
  <ul class="typeB">
    <li>
      <a href="#">
        <div class="pic"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/grid_w.svg" /></div>
        <div class="listTitle">側邊第一選項</div>
      </a>
    </li>
    <li>
      <a href="#">
        <div class="pic"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/setting_w.svg" /></div>
        <div class="listTitle">側邊第二選項</div>
      </a>
    </li>
    <li>
      <a href="#">
        <div class="pic"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/home_w.svg" /></div>
        <div class="listTitle">側邊第三選項</div>
      </a>
    </li>
    <li>
      <a href="#">
        <div class="pic"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/heart_w.svg" /></div>
        <div class="listTitle">側邊第四選項</div>
      </a>
    </li>
  </ul>
</div>
```

<!-- tabs:end -->
<style>
  .demo{
   position: relative;
    width: 160px;
    height: 300px;
  overflow:hidden;
  }
  .floatNav{
    position:absolute !important;
    bottom:auto !important;
    top:0 !important;
  }
</style>

<script>
  _toggleDropdown('.floatNav .floatSwitchBtn', '.floatNav .typeA'); //LP 內容搜尋
</script>
