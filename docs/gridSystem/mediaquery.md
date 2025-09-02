# Mediaquery

## 選擇優雅降級(Graceful Degradation)的開發流程

?> 目前大部分的網站規格是以 **Edge** 、 **FireFox** 、 **Chrome** 以及 **Safari** 為主流瀏覽器，且 UI 設計師產出之 mockup 大部分以 PC 版本作為風格確認，因此先以主流瀏覽器為測試對象，再往下兼容行動版以及各種不同瀏覽器的呈現。

### 如何自訂自己的斷點

可在`_variable.scss`自訂斷點，預設是以 `1399px`、`991px`、 `767px` 、 `575px` 為分界

```scss
//RWD尺寸設定
$screenSize: (
  //電腦
  notebook: 1399px,
  //平板
  tablet: 991px,
  //手機
  mobile: 767px,
  //極小尺寸
  xsMobile: 575px
);
```

### 設定 max

針對不同的瀏覽器寬度斷點設定，HyUI 提供快速套用變數的 `mixin` ，供開發者直覺地且輕易地在樣式表分別寫出不同的效果

!>請注意順序，如果是使用 HyUI 預設斷點 mixin 是由較寬螢幕至最小寬度依序設定，避免被覆蓋。

<!-- panels:start -->
<!-- div:left-panel -->

<h5>SCSS 設定</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
  @include screen('notebook') {
    width: 85%;
  }
  @include screen('tablet') {
    width: 55%;
  }
  @include screen('mobile') {
    width: 85%;
  }
  @include screen('xsMobile') {
    width: 85%;
  }
}
```

<!-- div:right-panel -->

<h5>CSS 輸出</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
}
@media screen and (max-width: 1399px) {
  .wrapper {
    width: 85%;
  }
}
@media screen and (max-width: 991px) {
  .wrapper {
    width: 55%;
  }
}
@media screen and (max-width: 767px) {
  .wrapper {
    width: 85%;
  }
}
@media screen and (max-width: 575px) {
  .wrapper {
    width: 85%;
  }
}
```

<!-- panels:end -->

### 設定 min

<!-- panels:start -->
<!-- div:left-panel -->
<h5>SCSS 設定</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
  @include screen('notebookMin') {
    width: 90%;
  }
  @include screenMin('tabletMin') {
    width: 55%;
  }
  @include screenMin('mobileMin') {
    width: 85%;
  }
  @include screenMin('xsMobileMin') {
    width: 85%;
  }
}
```

<!-- div:right-panel -->

<h5>CSS 輸出</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
}
@media screen and (min-width: 1400px) {
  .wrapper {
    width: 90%;
  }
}
@media screen and (min-width: 992px) {
  .wrapper {
    width: 55%;
  }
}
@media screen and (min-width: 768px) {
  .wrapper {
    width: 85%;
  }
}
@media screen and (min-width: 576px) {
  .wrapper {
    width: 85%;
  }
}
```

<!-- panels:end -->

### 自訂視窗尺寸 max screenMax

<!-- panels:start -->
<!-- div:left-panel -->
<h5>SCSS 設定</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
  @include screenMax('1200') {
    width: 90%;
  }
}
```

<!-- div:right-panel -->

<h5>CSS 輸出</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
}
@media screen and (max-width: 1200px) {
  .wrapper {
    width: 90%;
  }
}
```

<!-- panels:end -->

### 自訂視窗尺寸 min screenMin

<!-- panels:start -->
<!-- div:left-panel -->
<h5>SCSS 設定</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
  @include screenMin('1200') {
    width: 90%;
  }
}
```

<!-- div:right-panel -->

<h5>CSS 輸出</h5>

```scss
.wrapper {
  margin: 0 auto;
  width: 100%;
}
@media screen and (min-width: 1200px) {
  .wrapper {
    width: 90%;
  }
}
```

<!-- panels:end -->
