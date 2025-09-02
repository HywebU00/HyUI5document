# mixin / extend / function 引用列表

## 瀏覽器斷點

?> 原始設定：../scss/basic/mixins/`_mixin.scss`

```scss
//max-width
@include screen('notebook') {
} // max-width: 1366px
@include screen('tablet') {
} // max-width: 1024px
@include screen('mobile') {
} // max-width: 767px
@include screen('xsMobile') {
} // max-width: 550px

//min-width
@include screen('notebookMin') {
} // min-width: 1367px
@include screen('tabletMin') {
} // min-width: 1025px
@include screen('mobileMin') {
} // min-width: 768px
@include screen('xsMobileMin') {
} // min-width: 551px

//自訂
@include screenMax('1200') {
} // max-width: 1200px
@include screenMin('1200') {
} // min-width: 1200px
```

## 區塊寬度計算

有兩種方式：<br>

- 依照 12 等份計算寬度
- 不依照 12 等份計算寬度

```scss
// 設定 flex 的 margin gutter
// ../scss/_variable.scss
$flexTemplateGap: 20;

// 1.依照 12 等份計算寬度
// 使用方式
// 12等份中佔4等份，間距20px
width: flexWidth($flexTemplateGap, 4);

// 2.不依照 12 等份計算寬度
// 使用方式
// 100%中由4個區塊均分，間距20px
width: itemWidth($flexTemplateGap, 4);
```

## px 轉 rem

將 px 轉為 rem，例：20px = Rem(20) = 1.25rem

```scss
font-size: Rem(20);
```

## transition

```scss
// 預設 transition: all 0.3s ease;
@include transition();

// 可另外設定
@include transition(0.3, all, ease);
```

## 清除 li 格式

包含  
margin: 0;  
padding: 0;  
list-style: none;

```scss
@include liReset;
```

## 文字刪節號

包含  
 -webkit-line-clamp: $count;  
 display: -webkit-box !important;  
 -webkit-box-orient: vertical;  
 overflow: hidden;

!> 因為會改變 display 故使用時要注意

```scss
// 超過4行出現刪節號
@include lineClamp(4);
```

## 漸層功能

```scss
.gradient {
  @include gradient(#07c, #06f, vertical); // 垂直
  @include gradient(#07c, #06f, horizontal); // 水平
  @include gradient(#07c, #06f, diagonal); // 對角線
  @include gradient(#07c, #06f, circle); // 圓形
}
```

<style>
    .block-style{
  padding:2.2em 3em !important;
  background:#f8f8f8;
}
</style>
