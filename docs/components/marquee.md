# Marquee / 跑馬燈

?>相關 css：scss/components/`_marquee.scss`

HyUI 提供跑馬燈有兩種

- 使用 `swiper` 的輪播模組，需先在網頁中匯入外掛 CSS 及 js，可參考模組 [Slider 圖片輪播](components/slider.md)說明。
- 橫向循環模式

### `swiper` 的輪播模組

**範例**

<div class="marqueeSlider">
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  <div class="swiperBox">
    <div class="swiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。1</a>
        </div>
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。2</a>
        </div>
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。3</a>
        </div>
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。4</a>
        </div>
      </div>
    </div>
    <!-- swiper 往上-->
    <button class="swiperPrev swiperArrow">上一筆</button>
    <!-- swiper 往下-->
    <button class="swiperNext swiperArrow">下一筆</button>
  </div>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="marqueeSlider">
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  <div class="swiperBox">
    <div class="swiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。1</a>
        </div>
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。2</a>
        </div>
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。3</a>
        </div>
        <div class="swiper-slide">
          <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。4</a>
        </div>
      </div>
    </div>
    <!-- swiper 往上-->
    <button class="swiperPrev swiperArrow">上一筆</button>
    <!-- swiper 往下-->
    <button class="swiperNext swiperArrow">下一筆</button>
  </div>
</div>
```

#### **JS**

```javascript
const marqueeSlider = new Swiper('.marqueeSlider .swiper', {
  direction: 'vertical',
  // 切換箭頭
  navigation: {
    nextEl: '.marqueeSlider .swiperNext', //自行設定樣式
    prevEl: '.marqueeSlider .swiperPrev', //自行設定樣式
    disabledClass: 'swiperArrow-disabled', //不可點選樣式
  },
  autoplay: {
    delay: 5000,
  },
  on: {
    init: function (swiper) {
      swiperA11Fn(swiper);
    },
  },
});
```

<!-- tabs:end -->

<script>
  const marqueeSlider = new Swiper('.marqueeSlider .swiper', {
    direction: 'vertical',
    // 切換點
    // 切換箭頭
    navigation: {
      nextEl: '.marqueeSlider .swiperNext', //自行設定樣式
      prevEl: '.marqueeSlider .swiperPrev', //自行設定樣式
      disabledClass: 'swiperArrow-disabled', //不可點選樣式
    },
    autoplay: {
      delay: 5000,
    },
    on: {
      init: function (swiper) {
        swiperA11Fn(swiper);
      },
    },
  });
</script>

### 橫向循環模式

**範例**

<div class="marqueeSliderH">
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  <div class="marqueeBox">
    <div class="marqueeList">
      <div class="item">
        <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。因尼莎颱風來襲因尼莎颱風來襲因尼莎颱風來襲因尼莎颱風來襲。1</a>
      </div>
    </div>
  </div>
</div>

```html
<div class="marqueeSliderH">
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  <div class="marqueeBox">
    <div class="marqueeList">
      <div class="item">
        <a href="#"><span>2018-11-13</span>因尼莎颱風來襲，7/31下午2時之我國化學物質管理政策綱領第一次跨部會研商會取消。因尼莎颱風來襲因尼莎颱風來襲因尼莎颱風來襲因尼莎颱風來襲。1</a>
      </div>
    </div>
  </div>
</div>
```
