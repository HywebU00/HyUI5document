# SideNav 側邊選單

?>相關 css：scss/components/`_sideNav.scss`

只要在`mainBox`中增加`sideNav`的 aside，`main .container`會加上`display:flex;`的相關 css 設定。
側邊選單預設放置於畫面左方，`sideNavBtn`按鈕用於打開收合左側選單。  
側邊選單可以在`customize.js`中設定選項

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

// 亂數數字
function _randomNumber(max) {
  let letter = '1234567890';
  let number = '';

  for (let i = 0; i < max; i++) number += letter.charAt(Math.floor(Math.random() * letter.length));
  return number;
}

// 亂數英文字
function _randomLetter(max) {
  let letter = 'abcdefghijklmnopqrstuvwxyz';
  let text = '';

  for (let i = 0; i < max; i++) text += letter.charAt(Math.floor(Math.random() * letter.length));
  return text;
}function _jsSlideToggle(element, time = 200) {
  let ele = window.getComputedStyle(element);

  let display = ele.display;
  let speed = time;
  element.style.display = display;
  if (display === 'none') {
    element.style.display = 'block';
    let totalHeight = element.offsetHeight;
    element.style.overflow = 'hidden';
    element.style.height = '0px';
    element.style.transitionProperty = 'height';
    element.style.transitionDuration = `${speed}ms`;
    setTimeout(() => {
      element.style.height = `${totalHeight}px`;
    }, 0);
    setTimeout(() => {
      element.style.removeProperty('height');
      element.style.removeProperty('overflow');
      element.style.removeProperty('transition-duration');
      element.style.removeProperty('transition-property');
    }, speed);
  } else {
    let totalHeight2 = element.offsetHeight;
    element.style.overflow = 'hidden';
    element.style.height = `${totalHeight2}px`;
    element.style.transitionProperty = 'height';
    element.style.transitionDuration = `${speed}ms`;
    setTimeout(() => {
      element.style.height = `0px`;
    }, 0);
    setTimeout(() => {
      element.style.display = 'none';
      element.style.removeProperty('height');
      element.style.removeProperty('overflow');
      element.style.removeProperty('transition-duration');
      element.style.removeProperty('transition-property');
    }, speed);
  }
}
  function sideNav(options) {
  // RWD切換判斷，與_variable.scss 的 --RWDWidth連動
  const setRWDWidth = parseInt(window.getComputedStyle(document.documentElement).getPropertyValue('--RWDWidth'));
  const body = document.querySelector('body');
  const { showDefault = true, needLink = false, duration = 200, float = true } = options;
  const sideNav = document.querySelector('.sideNav');
  if (!sideNav) return;

  float ? sideNav.classList.add('typeA') : sideNav.classList.add('typeB');

  const nextOpen = sideNav.dataset.nextOpen;
  const nextClose = sideNav.dataset.nextClose;

  const sideMenu = sideNav.querySelector('nav#sideMenu');
  if (!sideMenu) return;
  const sideMenuContent = sideMenu.querySelector('.sideMenuContent');
  sideMenu.dataset.width = parseInt(getComputedStyle(sideMenuContent).width.replace('px', ''));
  const sideNavBtn = sideNav.querySelector('#sideNavBtn');
  const allTarget = sideNav.querySelectorAll('a, button, input, select');

  // 設定無障礙屬性
  // 按鈕
  sideNavBtn.setAttribute('aria-haspopup', 'true');
  sideNavBtn.setAttribute('aria-controls', 'sideMenu');
  // 選單
  sideMenu.setAttribute('aria-labelledby', 'sideNavBtn');
  sideMenu.setAttribute('role', 'navigation');

  if (sideNavBtn) {
    // 統一設定過渡效果

    function _setTransitionBtn(left = null, toLeft = null) {
      const checkDisplay = window.getComputedStyle(sideMenu).display === 'none';

      sideNavBtn.setAttribute('aria-expanded', checkDisplay ? 'false' : 'true');
      sideNavBtn.classList.toggle('active');

      if (window.outerWidth <= setRWDWidth && float) {
        sideNavBtn.style.transitionProperty = 'left';
        sideNavBtn.style.transitionDuration = `${duration}ms`;
        sideNavBtn.style.left = `${left}px`;
        setTimeout(() => {
          sideNavBtn.style.left = `${toLeft}px`;
        });
        setTimeout(() => {
          sideNavBtn.style.removeProperty('transition-duration');
          sideNavBtn.style.removeProperty('transition-property');
        }, duration);
      }
    }

function _jsSlideToggleWidth(element, time = 200) {
  let ele = window.getComputedStyle(element);
  let display = ele.display;
  let speed = time;
  element.style.display = display;
  if (display === 'none') {
    element.style.display = 'block';
    let totalWidth = element.offsetWidth;
    element.style.overflow = 'hidden';
    element.style.width = '0px';
    element.style.transitionProperty = 'width';
    element.style.transitionDuration = `${speed}ms`;
    setTimeout(() => {
      element.style.width = `${totalWidth}px`;
    }, 0);
    setTimeout(() => {
      element.style.removeProperty('width');
      element.style.removeProperty('overflow');
      element.style.removeProperty('transition-duration');
      element.style.removeProperty('transition-property');
    }, speed);
  } else {
    let totalWidth2 = element.offsetWidth;
    element.style.overflow = 'hidden';
    element.style.width = `${totalWidth2}px`;
    element.style.transitionProperty = 'width';
    element.style.transitionDuration = `${speed}ms`;
    setTimeout(() => {
      element.style.width = `0px`;
    }, 0);
    setTimeout(() => {
      element.style.display = 'none';
      element.style.removeProperty('width');
      element.style.removeProperty('overflow');
      element.style.removeProperty('transition-duration');
      element.style.removeProperty('transition-property');
    }, speed);
  }
}
    function _transitionToggle() {
      if ((window.outerWidth <= setRWDWidth && float) || window.outerWidth > setRWDWidth) {
        _jsSlideToggleWidth(sideMenu, 200);
      } else if (window.outerWidth <= setRWDWidth && !float) {
        _jsSlideToggle(sideMenu);
      }
    }
    sideNavBtn.addEventListener('click', () => {
      _transitionToggle();
      _setTransitionBtn();
    });
  }

  // 預設開啟/關閉
  if (showDefault) {
    // 按鈕
    sideNavBtn.setAttribute('aria-expanded', 'true');
    sideNavBtn.classList.add('active');
    // 選單
    sideMenu.style.display = 'block';
  } else {
    // 按鈕
    sideNavBtn.setAttribute('aria-expanded', 'false');
    sideNavBtn.setAttribute('aria-controls', 'sideMenu');
    // 選單
    sideMenu.style.display = 'none';
  }

  // 為含下層選單的 li 加上 hasChild 類別
  sideMenu.querySelectorAll('li ul').forEach((item) => item.parentNode.classList.add('hasChild'));

  // 設定所有含子選單項目的無障礙與點擊處理
  sideMenu.querySelectorAll('.hasChild').forEach((item) => {
    const uid = `sn_${_randomLetter(3)}${_randomNumber(3)}`;
    let childControl;
    if (!needLink) {
      childControl = item.querySelector('a');
      childControl.setAttribute('role', 'button');
    } else {
      item.classList.add('needLink');
      const nextBtn = document.createElement('button');
      nextBtn.classList.add('nextLvl');
      item.querySelector('a').insertAdjacentElement('afterend', nextBtn);
      nextBtn.setAttribute('type', 'button');
      nextBtn.setAttribute('aria-label', nextOpen);
      childControl = nextBtn;
    }
    const childUl = item.querySelector('ul');
    childControl.setAttribute('aria-expanded', 'false');
    childControl.setAttribute('aria-haspopup', 'true');
    childControl.setAttribute('id', uid);
    childControl.setAttribute('aria-controls', `${uid}_con`);
    childUl.setAttribute('id', `${uid}_con`);
    childUl.setAttribute('aria-labelledby', uid);
    childControl.addEventListener('click', (e) => {
      e.preventDefault();
      _toggleAccordion(childControl, 'ul', item);
    });
  });

  // 手風琴切換函式
  function _toggleAccordion(control, selector, parent) {
    const content = control.parentNode.querySelector(selector);
    const isVisible = getComputedStyle(content).display !== 'none';
    control.setAttribute('aria-expanded', isVisible ? 'false' : 'true');
    parent.classList.toggle('active');
    _jsSlideToggle(content);
    if (needLink) {
      control.setAttribute('aria-label', isVisible ? nextOpen : nextClose);
    }
    // 收合同層其他項目
    const sibling = [...control.parentNode.parentNode.children].filter((item) => item !== parent);

    sibling.forEach((item) => {
      item.querySelector(selector) !== null ? _jsSlideUp(item.querySelector(selector)) : null;
      if (needLink) {
        item.querySelector('button')?.setAttribute('aria-expanded', 'false');
        item.querySelector('button')?.setAttribute('aria-label', nextOpen);
      } else {
        item.querySelector('a').setAttribute('aria-expanded', 'false');
      }
      item.classList.remove('active');
    });
  }

  let checkRwd = window.outerWidth < setRWDWidth;
  // 鍵盤無障礙設定（僅限 RWD 狀態下有效）
  body.addEventListener('keydown', (e) => {
    if (checkRwd && sideNavBtn.getAttribute('aria-expanded') === 'true') {
      const focusable = [...allTarget].filter((item) => item.getBoundingClientRect().height !== 0);
      const lastFocusable = focusable.at(-1);
      if (e.code === 'Tab') {
        if (e.shiftKey && e.target === allTarget[0]) {
          e.preventDefault();
          lastFocusable.focus();
        } else if (!e.shiftKey && e.target === lastFocusable) {
          e.preventDefault();
          sideNavBtn.focus();
        }
      }
    }
  });

  // 視窗載入與重置事件：調整響應式設定
  const _checkRwdFn = () => {
    if (window.outerWidth <= setRWDWidth) {
      checkRwd = true;
      sideNavBtn.classList.remove('active');
      sideNavBtn.setAttribute('aria-expanded', 'false');
      if (float) {
        sideNavBtn.style.left = '';
        sideNavBtn.style.top = `80px`;
        sideMenu.removeAttribute('style');
      } else {
        _jsSlideUp(sideMenu);
      }
    } else if (window.outerWidth > setRWDWidth && checkRwd === true) {
      checkRwd = false;
      sideNavBtn.classList.add('active');
      sideNavBtn.setAttribute('aria-expanded', 'true');
      sideMenu.removeAttribute('style');
      if (!float) _jsSlideDown(sideMenu);
    }
  };
  _checkRwdFn();
  window.addEventListener('resize', () => _checkRwdFn());
}
sideNav({
  needLink: false, // 如果同時需要連結和下層功能時
});
</script>
