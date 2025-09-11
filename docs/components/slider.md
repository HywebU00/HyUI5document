# Slider 圖片輪播

?>相關 css：vendor/swiper/`swiper-bundle.min.css`<br>
相關 css：scss/components/`_slider.scss_`

HyUI 使用 `swiper` 的輪播模組，目前 hyUI **vendor** 內含 **swiper**，如需要最新版，請到 [swiper](https://swiperjs.com/) 官網下載。<br/>
[中文版](https://www.swiper.com.cn/)

## 請在網頁中匯入 swiper 外掛

**swiper** 屬於外掛，故放在 `vendor` 資料夾裡，包括所有的圖檔、js、css

## 匯入外掛 CSS

```html
<link rel="stylesheet" type="text/css" href="vendor/swiper/swiper-bundle.min.css" />
```

## 匯入 JS

```html
<script src="vendor/swiper/swiper-bundle.min.js"></script>
```

## swiper 基本 Html 結構

```html
<div class="swiper">
  <div class="swiper-wrapper">
    <!-- 輪播內容 -->
    <div class="swiper-slide">Slide 1</div>
    <div class="swiper-slide">Slide 2</div>
    <div class="swiper-slide">Slide 3</div>
    ...
  </div>
  <!-- 圓點 -->
  <div class="swiper-pagination"></div>

  <!-- 左右切換按鈕 -->
  <div class="swiper-button-prev"></div>
  <div class="swiper-button-next"></div>
</div>
```

- swiper 不會強制圓點/箭頭放置位置，只要 class 有對應到就可以。
- swiper-wrapper 不要設定任何會影響寬度或是排版的 css，例如 padding/justify-content

## swiper 的基本設定

使用設定以 `swiper` 官方文件為準。<br/>
**swiper** 功能非常多可自行到 [中文版 API](https://www.swiper.com.cn/api/index.html) 觀看

```javascript
const mpSlider = new Swiper('.mpSlider .swiper', {
  slidesPerView: 1, //顯示筆數
  spaceBetween: 20, //每筆之間的距離
  navigation: {
    nextEl: '.mpSlider .swiperNext', //下一筆class，無障礙設定關係需要增加.swiperNext
    prevEl: '.mpSlider .swiperPrev', //前一筆class，無障礙設定關係需要增加.swiperPrev
    disabledClass: 'swiperArrow-disabled', //不可點選樣式
  },
  pagination: {
    //顯示圓點
    el: '.swiperDots', //圓點 class
    type: 'bullets', //樣式參考 https://www.swiper.com.cn/api/pagination/299.html
    clickable: true, //設定後圓點才可以點擊
  },
  autoplay: {
    //自動播放
    delay: 5000, //自動播放的間隔
    stopOnLastSlide: true, // 停在最後一筆，開啟loop後無效。
  },
  loop: true, //無限輪播
  effect: 'fade', //淡入
  fadeEffect: {
    crossFade: true, //上一筆淡出，false上一筆不淡出，下一筆疊在上方
  },
  lazy: true,
  breakpoints: {
    //   rwd 切換數量功能
    1000: {
      slidesPerView: 1,
    },
  },
  on: {
    init: function (swiper) {
      swiperA11Fn(swiper); // 有圓點時，圓點的無障礙，autoPlay切換按鈕功能
    },
  },
});
swiperNavKeyDownFn(sliderFor.thumbs.swiper, sliderFor); //有小縮圖時，需要使用此功能來設定鍵盤操作，下面會詳述
```

## 大圖輪播範例

<div class="mpSlider flexTpl_12 full">
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  <div class="swiperBox">
    <!-- swiper 上一張-->
    <button class="swiperPrev swiperArrow">上一張</button>
    <div class="swiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <a href="#">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/banner.png" alt="第1張圖說" />
            </div>
          </a>
        </div>
        <div class="swiper-slide">
          <a href="#">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/banner.png" alt="第1張圖說" />
            </div>
          </a>
        </div>
      </div>
    </div>
    <!-- swiper 下一張-->
    <button class="swiperNext swiperArrow">下一張</button>
  </div>
  <!--分頁-->
  <div class="swiperPagination"></div>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="mpSlider flexTpl_12 full">
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  <div class="swiperBox">
    <!-- swiper 上一張-->
    <button class="swiperPrev swiperArrow">上一張</button>
    <div class="swiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <a href="#">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/banner.png" alt="第1張圖說" />
            </div>
          </a>
        </div>
        <div class="swiper-slide">
          <a href="#">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/banner.png" alt="第1張圖說" />
            </div>
          </a>
        </div>
      </div>
    </div>
    <!-- swiper 下一張-->
    <button class="swiperNext swiperArrow">下一張</button>
  </div>
  <!--分頁-->
  <div class="swiperPagination"></div>
</div>
```

#### **JS**

```javascript
const mpSlider = new Swiper('.mpSlider .swiper', {
  // 切換點
  pagination: {
    el: '.mpSlider .swiperPagination',
    clickable: true,
  },
  // 切換箭頭
  navigation: {
    nextEl: '.mpSlider .swiperNext', //自行設定樣式
    prevEl: '.mpSlider .swiperPrev', //自行設定樣式
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

## 廣告輪播範例

<div class="linkSlider">
<div class="swiperBox">
  <!-- swiper 左邊箭頭-->
  <button type="button" class="swiperPrev swiperArrow">上一筆</button>
  <div class="swiper">
    <div class="swiper-wrapper">
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_01.jpg" alt="第1張圖說" />
          </div>
        </a>
      </div>
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_02.jpg" alt="第2張圖說" />
          </div>
        </a>
      </div>
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_03.jpg" alt="第3張圖說" />
          </div>
        </a>
      </div>
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_04.jpg" alt="第4張圖說" />
          </div>
        </a>
      </div>
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_05.jpg" alt="第5張圖說" />
          </div>
        </a>
      </div>
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_06.jpg" alt="第6張圖說" />
          </div>
        </a>
      </div>
      <div class="swiper-slide">
        <a class="item" href="#">
          <div class="pic">
            <img src="https://hywebu00.github.io/HyUI5/images/demo/ad_07.jpg" alt="第7張圖說" />
          </div>
        </a>
      </div>
    </div>
  </div>
  <!-- swiper 右邊箭頭-->
  <button type="button" class="swiperNext swiperArrow">下一筆</button>
</div>
<!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
<button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
  </div>

<!-- tabs:start -->

#### **HTML**

```html
<!-- 廣告輪播   start -->
<div class="linkSlider">
  <div class="swiperBox">
    <!-- swiper 左邊箭頭-->
    <button type="button" class="swiperPrev swiperArrow">上一筆</button>
    <div class="swiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <a class="item" href="#">
            <div class="pic">
              <img src="images/demo/ad_01.jpg" alt="第1張圖說" />
            </div>
          </a>
        </div>
      </div>
    </div>
    <!-- swiper 右邊箭頭-->
    <button type="button" class="swiperNext swiperArrow">下一筆</button>
  </div>
  <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
  <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
</div>
<!-- 廣告輪播   end -->
```

#### **JS**

```javascript
const linkSlider = new Swiper('.linkSlider .swiper', {
  slidesPerView: 1,
  spaceBetween: 20,
  slideToClickedSlide: true,
  loop: false,
  // 切換箭頭
  navigation: {
    nextEl: '.linkSlider .swiperNext', //自行設定樣式
    prevEl: '.linkSlider .swiperPrev', //自行設定樣式
    disabledClass: 'swiperArrow-disabled', //不可點選樣式
  },
  breakpoints: {
    100: {
      slidesPerView: 2,
    },
    767: {
      slidesPerView: 3,
    },
    1000: {
      slidesPerView: 4,
    },
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

## 照片輪播範例

<div class="cpAlbum">
  <!-- 大圖slider Start -->
  <div class="sliderFor">
    <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
    <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
    <div class="swiperBox">
      <div class="swiper">
        <div class="swiper-wrapper">
          <div class="swiper-slide">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/01.jpg" alt="第1張圖說" />
            </div>
          </div>
          <div class="swiper-slide">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/02.jpg" alt="第2張圖說" />
            </div>
          </div>
          <div class="swiper-slide">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/03.jpg" alt="第3張圖說" />
            </div>
          </div>
          <div class="swiper-slide">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/04.jpg" alt="第4張圖說" />
            </div>
          </div>
          <div class="swiper-slide">
            <div class="pic">
              <img src="https://hywebu00.github.io/HyUI5/images/demo/05.jpg" alt="第5張圖說" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <!--分頁-->
    <div class="swiperPagination"></div>
  </div>
  <!-- 大圖slider End -->

  <!-- 小圖slider Start -->
  <div class="navSlider">
    <div class="swiperBox">
      <div class="swiper">
        <!--前一筆-->
        <button type="button" class="swiperPrev swiperArrow"></button>
        <div class="swiper-wrapper">
          <div class="swiper-slide">
            <div class="item">
              <div class="pic">
                <img src="https://hywebu00.github.io/HyUI5/images/demo/01.jpg" alt />
              </div>
              <div class="caption"><span>第1張圖說</span></div>
            </div>
          </div>
          <div class="swiper-slide">
            <div class="item">
              <div class="pic">
                <img src="https://hywebu00.github.io/HyUI5/images/demo/02.jpg" alt />
              </div>
              <div class="caption"><span>第2張圖說</span></div>
            </div>
          </div>
          <div class="swiper-slide">
            <div class="item">
              <div class="pic">
                <img src="https://hywebu00.github.io/HyUI5/images/demo/03.jpg" alt />
              </div>
              <div class="caption"><span>第3張圖說</span></div>
            </div>
          </div>
          <div class="swiper-slide">
            <div class="item">
              <div class="pic">
                <img src="https://hywebu00.github.io/HyUI5/images/demo/04.jpg" alt />
              </div>
              <div class="caption"><span>第4張圖說</span></div>
            </div>
          </div>
          <div class="swiper-slide">
            <div class="item">
              <div class="pic">
                <img src="https://hywebu00.github.io/HyUI5/images/demo/05.jpg" alt />
              </div>
              <div class="caption"><span>第5張圖說</span></div>
            </div>
          </div>
        </div>
        <!--下一筆-->
        <button type="button" class="swiperNext swiperArrow"></button>
      </div>
    </div>
  </div>
  <!-- 小圖slider End -->
</div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="cpAlbum">
  <!-- 大圖slider Start -->
  <div class="sliderFor">
    <!-- 如果需要自動播放，無障礙需要增加此按鈕 -->
    <button type="button" class="autoPlaySwitch" data-info-play="暫停中，點我播放" data-info-stop="播放中，點我暫停"></button>
    <div class="swiperBox">
      <div class="swiper">
        <div class="swiper-wrapper">
          <div class="swiper-slide">
            <div class="pic">
              <img src="images/demo/01.jpg" alt="第1張圖說" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <!--分頁-->
    <div class="swiperPagination"></div>
  </div>
  <!-- 大圖slider End -->

  <!-- 小圖slider Start -->
  <div class="navSlider">
    <div class="swiperBox">
      <div class="swiper">
        <!--前一筆-->
        <button type="button" class="swiperPrev swiperArrow"></button>
        <div class="swiper-wrapper">
          <div class="swiper-slide">
            <div class="item">
              <div class="pic">
                <img src="images/demo/01.jpg" alt />
              </div>
              <div class="caption"><span>第1張圖說</span></div>
            </div>
          </div>
        </div>
        <!--下一筆-->
        <button type="button" class="swiperNext swiperArrow"></button>
      </div>
    </div>
  </div>
  <!-- 小圖slider End -->
</div>
```

#### **JS**

```javascript
const sliderFor = new Swiper('.sliderFor .swiper', {
  slidesPerView: 1,
  effect: 'fade',
  fadeEffect: {
    crossFade: true,
  },
  pagination: {
    el: '.sliderFor .swiperPagination',
    type: 'fraction',
  },
  autoplay: {
    delay: 5000,
  },
  lazy: true,
  thumbs: {
    swiper: {
      el: '.navSlider .swiper',
      spaceBetween: 20,
      slideToClickedSlide: true,
      slidesPerView: 4,
      watchSlidesVisibility: true,
      navigation: {
        nextEl: '.navSlider .swiperNext',
        prevEl: '.navSlider .swiperPrev',
        disabledClass: 'swiperArrow-disabled', //不可點選樣式
      },
      breakpoints: {
        100: {
          slidesPerView: 2,
        },
        767: {
          slidesPerView: 3,
        },
        1000: {
          slidesPerView: 4,
        },
      },
    },
    autoScrollOffset: 1,
  },
  on: {
    init: function (swiper) {
      swiperA11Fn(swiper);
    },
  },
});
swiperNavKeyDownFn(sliderFor.thumbs.swiper, sliderFor);
```

<!-- tabs:end -->

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@8/swiper-bundle.min.css" />
<style>
.swiperBox{
  margin:4em 0;
  position:relative;
}
.swiperDots{
  position:relative;
  bottom:0px !important;
}
.swiper-slide {
  position:relative;
}
.navSlider,
.bannerSlider,
.adSlider{
  position:relative;
  overflow:hidden;
}
</style>
<script>
function swiperA11Fn(swiper) {
  // 圓點
  let noActive = 0;
  swiper.slides.filter((elem, i) => {
    if (elem.classList.contains('swiper-slide-thumb-active')) {
      noActive = i;
    }
  });
  const swiperSlide = swiper.el.querySelectorAll('.item');
  swiperSlide.forEach((elem, idx) => {
    elem.setAttribute('role', 'button');
    elem.setAttribute('tabindex', '0');
    if (idx === noActive) {
      elem.setAttribute('aria-pressed', 'true');
    } else {
      elem.setAttribute('aria-pressed', 'false');
    }
    elem.addEventListener('click', (e) => {
      elem.setAttribute('aria-pressed', 'true');
      let sibling = [...swiperSlide].filter((item) => item !== elem);
      sibling.forEach((j) => j.setAttribute('aria-pressed', 'false'));
    });
  });
  // swiperAutoPlay切換功能
  const autoPlaySwitch = swiper.el.parentNode.parentNode.querySelector('.autoPlaySwitch');
  if (!autoPlaySwitch) return;
  let nowState = swiper.autoplay.running ? true : false;
  let infoPlay = autoPlaySwitch.dataset.infoPlay;
  let infoStop = autoPlaySwitch.dataset.infoStop;
  nowState ? autoPlaySwitch.classList.add('stop') : autoPlaySwitch.classList.add('play');
  autoPlaySwitch.setAttribute('aria-label', infoStop);
  autoPlaySwitch.setAttribute('data-altlabel', infoPlay);
  autoPlaySwitch.addEventListener('click', (e) => {
    if (nowState) {
      nowState = false;
      swiper.autoplay.stop();
      autoPlaySwitch.classList.add('play');
      autoPlaySwitch.classList.remove('stop');
      autoPlaySwitch.setAttribute('aria-label', infoPlay);
      autoPlaySwitch.setAttribute('data-altlabel', infoStop);
    } else {
      nowState = true;
      swiper.autoplay.start();
      autoPlaySwitch.classList.add('stop');
      autoPlaySwitch.classList.remove('play');
      autoPlaySwitch.setAttribute('aria-label', infoStop);
      autoPlaySwitch.setAttribute('data-altlabel', infoPlay);
    }
  });
  swiper.slides.length === 1 ? autoPlaySwitch.remove() : null;
}
function swiperNavKeyDownFn(swiper, mainSwiper) {
  const body = document.querySelector('body');
  if (!swiper) return;
  swiper.slides.forEach((elem, idx) => {
    elem.dataset.swiperSlideIndex = idx;
  });
  body.addEventListener('keydown', (e) => {
    if (e.code === 'Enter' && e.target.parentNode.dataset.swiperSlideIndex !== undefined) {
      let index = e.target.parentNode.dataset.swiperSlideIndex;
      let swiperSlide = e.target.parentNode.parentNode.querySelectorAll('.item');
      mainSwiper.slideTo(index, 1000, false);
      e.target.setAttribute('aria-pressed', 'true');
      let sibling = [...swiperSlide].filter((item) => item !== e.target);
      sibling.forEach((j) => j.setAttribute('aria-pressed', 'false'));
    }
  });
}
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
// ----- MP 輪播 ---------------------------------------------------
const mpSlider = new Swiper('.mpSlider .swiper', {
// 切換點
pagination: {
el: '.mpSlider .swiperPagination',
clickable: true,
},
// 切換箭頭
navigation: {
nextEl: '.mpSlider .swiperNext', //自行設定樣式
prevEl: '.mpSlider .swiperPrev', //自行設定樣式
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
const linkSlider = new Swiper('.linkSlider .swiper', {
slidesPerView: 1,
spaceBetween: 20,
slideToClickedSlide: true,
loop: false,
// 切換箭頭
navigation: {
nextEl: '.linkSlider .swiperNext', //自行設定樣式
prevEl: '.linkSlider .swiperPrev', //自行設定樣式
disabledClass: 'swiperArrow-disabled', //不可點選樣式
},
breakpoints: {
100: {
slidesPerView: 2,
},
767: {
slidesPerView: 3,
},
1000: {
slidesPerView: 4,
},
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
  const sliderFor = new Swiper('.sliderFor .swiper', {
    slidesPerView: 1,
    effect: 'fade',
    fadeEffect: {
      crossFade: true,
    },
    pagination: {
      el: '.sliderFor .swiperPagination',
      type: 'fraction',
    },
    autoplay: {
      delay: 5000,
    },
    lazy: true,
    thumbs: {
      swiper: {
        el: '.navSlider .swiper',
        spaceBetween: 20,
        slideToClickedSlide: true,
        slidesPerView: 4,
        watchSlidesVisibility: true,
        navigation: {
          nextEl: '.navSlider .swiperNext',
          prevEl: '.navSlider .swiperPrev',
          disabledClass: 'swiperArrow-disabled', //不可點選樣式
        },
        breakpoints: {
          100: {
            slidesPerView: 2,
          },
          767: {
            slidesPerView: 3,
          },
          1000: {
            slidesPerView: 4,
          },
        },
      },
      autoScrollOffset: 1,
    },
    on: {
      init: function (swiper) {
        swiperA11Fn(swiper);
      },
    },
  });
  swiperNavKeyDownFn(sliderFor.thumbs.swiper, sliderFor);
</script>
