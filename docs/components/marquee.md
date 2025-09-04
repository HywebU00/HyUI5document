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

  function marquee() {
  const marquee = document.querySelectorAll('.marqueeSliderH');
  if (marquee.length === 0) return;
  marquee.forEach((i) => {
    const marqueeBox = i.querySelector('.marqueeBox');
    const marqueeList = i.querySelector('.marqueeList');
    const autoPlaySwitch = i.querySelector('.autoPlaySwitch');
    let marqueeBoxWidth = marqueeBox.offsetWidth;
    let marqueeListWidth = marqueeList.offsetWidth;

    let isPaused = false;
    let isHover = false;
    let sliderMovePx = 0;

    window.addEventListener('resize', () => {
      marqueeBoxWidth = marqueeBox.offsetWidth;
      marqueeListWidth = marqueeList.offsetWidth;
    });

    for (let i = 0; (marqueeListWidth * i) / marqueeBoxWidth < 1; i++) {
      let cloneList = marqueeList.cloneNode(true);

      cloneList.querySelectorAll('a').forEach((value) => {
        value.setAttribute('tabindex', '-1');
      });
      marqueeList.insertAdjacentElement('afterend', cloneList);
    }
    let allList = marqueeBox.querySelectorAll('.marqueeList');
    function _marqueeMove() {
      requestAnimationFrame(_marqueeMove);
      if (isHover || isPaused) return;
      sliderMovePx++;

      if (sliderMovePx <= marqueeListWidth) {
        allList.forEach((value) => {
          value.style.transform = `translateX(-${sliderMovePx}px)`;
        });
      } else {
        sliderMovePx = 0;
      }
    }
    _marqueeMove();
    marqueeBox.addEventListener('mouseenter', () => {
      isHover = true;
    });
    marqueeBox.addEventListener('mouseleave', () => {
      isHover = false;
    });
    marqueeBox.addEventListener('keyup', (e) => {
      if (e.code === 'Tab') {
        e.preventDefault();
        sliderMovePx = -1;
        setTimeout(() => {
          isPaused = true;
        });
        autoPlaySwitch.classList.add('play');
        autoPlaySwitch.classList.remove('stop');
        autoPlaySwitch.setAttribute('aria-label', infoPlay);
        autoPlaySwitch.setAttribute('data-altlabel', infoStop);
      }
    });

    // autoPlay切換功能

    if (!autoPlaySwitch) return;
    let infoPlay = autoPlaySwitch.dataset.infoPlay;
    let infoStop = autoPlaySwitch.dataset.infoStop;
    autoPlaySwitch.classList.add('stop');
    autoPlaySwitch.setAttribute('aria-label', infoStop);
    autoPlaySwitch.setAttribute('data-altlabel', infoPlay);

    autoPlaySwitch.addEventListener('click', (e) => {
      if (!isPaused) {
        isPaused = true;
        autoPlaySwitch.classList.add('play');
        autoPlaySwitch.classList.remove('stop');
        autoPlaySwitch.setAttribute('aria-label', infoPlay);
        autoPlaySwitch.setAttribute('data-altlabel', infoStop);
      } else {
        isPaused = false;
        autoPlaySwitch.classList.add('stop');
        autoPlaySwitch.classList.remove('play');
        autoPlaySwitch.setAttribute('aria-label', infoStop);
        autoPlaySwitch.setAttribute('data-altlabel', infoPlay);
      }
    });
  });
}
window.addEventListener('load', () => marquee());

</script>
