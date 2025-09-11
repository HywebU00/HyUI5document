# Header 頁首

?>相關 css：scss/template/`_header.scss`<br>

**頁首**由 **header** 標籤包覆，目前已預先設定 **h1 (logo 圖檔)** 、**navigation** 、 **search** 、 **menu** 等元素。

**內含預設模組可參考**

- [Navigation 導覽列](components/topnav.md)
- [Menu 主選單](components/menu.md)

以下模組依照無障礙 `tab`遊走順序擺放，如無特殊需求，皆依照由上到下、由左到右之順序呈現。

頁首模組皆已設定響應式風格樣式，目前斷點預設為 `991px` ，如需要更改斷點，請至`main.js`更改斷點變數，以及`_variable.scss`更改斷點變數。

HyUI5 更新將 header 拆成`headTop`和`mainMenu`區塊，方便背景延伸設計處理。

**範例**

<header>
  <a class="accessKeyItem" href="#aU" id="aU" accesskey="U" aria-label="功能區塊">:::</a>
<div class="headTop">
<div class="container">
<!-- 手機版主選單按鈕 Start -->
<button id="mobileMainMenuBtn" type="button">主選單</button>
<!-- 手機版主選單按鈕 End -->
<!-- 網站標題 Start -->
<h1>
<a href="index.html"><img src="https://hywebu00.github.io/HyUI5/images/footer_logo.png" alt="網站標題" />HyUI<span>Kit5</span></a>
</h1>
<!-- 網站標題 End -->
<!-- navigation Start -->
<nav class="topNav" role="navigation" aria-label="頁首功能列">
<!-- navList Start -->
<div class="navList">
<ul>
<li><a href="#">回首頁</a></li>
<li><a href="#">網站導覽</a></li>
<li><a href="#">常見問答</a></li>
</ul>
</div>
<!-- navList End -->
<!-- subNavList Start -->
<div class="subNavList">
<!-- fontSize Start -->
<div class="fontSize sliderFn">
<button type="button">文字大小</button>
<ul>
<li><button type="button" class="smallSize">小</button></li>
<li><button type="button" class="mediumSize">中</button></li>
<li><button type="button" class="largeSize">大</button></li>
</ul>
</div>
<!-- fontSize End -->
<!-- language Start -->
<div class="language sliderFn">
<button type="button">語言選擇</button>
<ul id="languageList">
<li><a href="#">繁體中文</a></li>
<li><a href="#">简体中文</a></li>
<li><a href="#">ENGLISH</a></li>
</ul>
</div>
<!-- language End -->
<!-- topSearch 按鈕 Start -->
<div class="topSearch sliderFn">
<button id="topSearchBtn" type="button">網站搜尋</button>
</div>
<!-- topSearch 按鈕 End -->
</div>
<!-- subNavList End -->
</nav>
<!-- navigation End -->
<!-- topSearch 手機版按鈕 Start -->
<button id="mobileSearchBtn" type="button" aria-label="搜尋按鈕"></button>
<!-- topSearch 手機版按鈕 End -->
<!-- topSearch 內容 Start -->
<div class="webSearch" role="search">
<div class="webSearchContent">
<div class="formList">
<label for="topSearchInput" class="srOnly">搜尋</label>
<input name="topSearchInput" id="topSearchInput" type="text" placeholder="請輸入文字" accesskey="S" aria-label="搜尋網站內容" />
<button type="button" class="btnPrimary">查詢</button>
<button type="button">進階搜尋</button>
</div>
<div class="hotKeyword">
<ul>
<li><a href="#">熱門熱門</a></li>
<li><a href="#">查詢</a></li>
<li><a href="#">字詞三</a></li>
</ul>
</div>
</div>
</div>
<!-- topSearch 內容 End -->
</div>
</div>
<!-- noscript -->
<noscript>
您的瀏覽器不支援 JavaScript 語法，JavaScript 語法並不影響內容的陳述。您可使用按鍵盤上的 Ctrl 鍵+ (+)鍵放大/(-)鍵縮小來改變字型大小；回到上一頁可使用瀏覽器提供的 Alt+左方向鍵(←) 快速鍵功能；列印可使用瀏覽器提供的(Ctrl+P)功能。您的瀏覽器，不支援 script 語法，若您的瀏覽器無法支援請點選此超連結
<a href="#">網站導覽</a>
</noscript>
<!-- menu Start -->
<div class="mainMenu">
<div class="container">
<nav class="menu" role="navigation" aria-label="主選單">
<ul>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li><a href="http://www.google.com">第一層有連結</a></li>
<li>
<a href="http://www.google.com">第一層有連結</a>
<ul>
<li><a href="http://www.google.com">第二層有連結</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
<li>
<a href="http://www.google.com">第二層有連結</a>
<ul>
<li>
<a href="http://www.google.com">第三層選單有下層</a>
<ul>
<li><a href="#">第四層選單</a></li>
<li><a href="#">第四層選單</a></li>
</ul>
</li>
<li>
<a href="http://www.google.com">第三層選單有連結</a>
</li>
<li><a href="#">第三層選單</a></li>
</ul>
</li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li>
<a href="#">第二層選單</a>
<ul>
<li><a href="#">第三層選單</a></li>
<li>
<a href="#">第三層選單</a>
<ul>
<li>
<a href="http://www.google.com">第四層選單有下層</a>
<ul>
<li><a href="#">第五層選單</a></li>
<li><a href="#">第五層選單</a></li>
</ul>
</li>
<li>
<a href="http://www.google.com">第四層選單有連結</a>
</li>
<li><a href="#">第四層選單</a></li>
</ul>
</li>
<li><a href="#">第三層選單</a></li>
<li><a href="#">第三層選單</a></li>
</ul>
</li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
<li>
<a href="#">第一層選單</a>
<ul>
<li><a href="#">第二層選單</a></li>
<li>
<a href="#">第二層選單</a>
<ul>
<li>
<a href="http://www.google.com">第三層選單有下層</a>
<ul>
<li><a href="#">第四層選單</a></li>
<li><a href="#">第四層選單</a></li>
</ul>
</li>
<li>
<a href="http://www.google.com">第三層選單有連結</a>
</li>
<li><a href="#">第三層選單</a></li>
</ul>
</li>
<li><a href="#">第二層選單</a></li>
<li><a href="#">第二層選單</a></li>
</ul>
</li>
</ul>
</nav>
</div>
</div>
<!-- menu End -->
</header>

<!-- tabs:start -->

#### **HTML**

```html
<!-- header Start -->
<header>
  <div class="headTop">
    <div class="container">
      <!-- 手機版主選單按鈕 Start -->
      <button id="mobileMainMenuBtn" type="button">主選單</button>
      <!-- 手機版主選單按鈕 End -->
      <!-- 網站標題 Start -->
      <h1>
        <a href="index.html"><img src="images/footer_logo.png" alt="網站標題" />HyUI<span>Kit5</span></a>
      </h1>
      <!-- 網站標題 End -->
      <!-- navigation Start -->
      <nav class="topNav" role="navigation" aria-label="頁首功能列">
        <a class="accessKeyItem" href="#aU" id="aU" accesskey="U" aria-label="功能區塊">:::</a>
        <!-- navList Start -->
        <div class="navList">
          <ul>
            <li><a href="#">回首頁</a></li>
            <li><a href="#">網站導覽</a></li>
            <li><a href="#">常見問答</a></li>
          </ul>
        </div>
        <!-- navList End -->
        <!-- submenuBox Start -->
        <div class="submenuBox">
          <!-- fontSize Start -->
          <div class="fontSize sliderFn">
            <button type="button">文字大小</button>
            <ul>
              <li><button type="button" class="smallSize">小</button></li>
              <li><button type="button" class="mediumSize">中</button></li>
              <li><button type="button" class="largeSize">大</button></li>
            </ul>
          </div>
          <!-- fontSize End -->
          <!-- language Start -->
          <div class="language sliderFn">
            <button type="button">語言選擇</button>
            <ul id="languageList">
              <li><a href="#">繁體中文</a></li>
              <li><a href="#">简体中文</a></li>
              <li><a href="#">ENGLISH</a></li>
            </ul>
          </div>
          <!-- language End -->
          <!-- topSearch 按鈕 Start -->
          <div class="topSearch sliderFn">
            <button id="topSearchBtn" type="button">網站搜尋</button>
          </div>
          <!-- topSearch 按鈕 End -->
        </div>
        <!-- submenuBox End -->
      </nav>
      <!-- navigation End -->
      <!-- topSearch 手機版按鈕 Start -->
      <button id="mobileSearchBtn" type="button" aria-label="搜尋按鈕"></button>
      <!-- topSearch 手機版按鈕 End -->
      <!-- topSearch 內容 Start -->
      <div class="webSearch" role="search">
        <div class="webSearchContent">
          <div class="formList">
            <label for="topSearchInput" class="srOnly">搜尋</label>
            <input name="topSearchInput" id="topSearchInput" type="text" placeholder="請輸入文字" accesskey="S" aria-label="搜尋網站內容" />
            <button type="button" class="btnPrimary">查詢</button>
            <button type="button">進階搜尋</button>
          </div>
          <div class="hotKeyword">
            <ul>
              <li><a href="#">熱門熱門</a></li>
              <li><a href="#">查詢</a></li>
              <li><a href="#">字詞三</a></li>
            </ul>
          </div>
        </div>
      </div>
      <!-- topSearch 內容 End -->
    </div>
  </div>
  <!-- noscript -->
  <noscript>
    您的瀏覽器不支援JavaScript語法，JavaScript語法並不影響內容的陳述。您可使用按鍵盤上的Ctrl鍵+ (+)鍵放大/(-)鍵縮小來改變字型大小；回到上一頁可使用瀏覽器提供的 Alt+左方向鍵(←) 快速鍵功能；列印可使用瀏覽器提供的(Ctrl+P)功能。您的瀏覽器，不支援script語法，若您的瀏覽器無法支援請點選此超連結
    <a href="#">網站導覽</a>
  </noscript>
  <!-- menu Start -->
  <div class="mainMenu">
    <div class="container">
      <nav class="menu" role="navigation" aria-label="主選單">
        <ul>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li><a href="http://www.google.com">第一層有連結</a></li>
          <li>
            <a href="http://www.google.com">第一層有連結</a>
            <ul>
              <li><a href="http://www.google.com">第二層有連結</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
              <li>
                <a href="http://www.google.com">第二層有連結</a>
                <ul>
                  <li>
                    <a href="http://www.google.com">第三層選單有下層</a>
                    <ul>
                      <li><a href="#">第四層選單</a></li>
                      <li><a href="#">第四層選單</a></li>
                    </ul>
                  </li>
                  <li>
                    <a href="http://www.google.com">第三層選單有連結</a>
                  </li>
                  <li><a href="#">第三層選單</a></li>
                </ul>
              </li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li>
                <a href="#">第二層選單</a>
                <ul>
                  <li><a href="#">第三層選單</a></li>
                  <li>
                    <a href="#">第三層選單</a>
                    <ul>
                      <li>
                        <a href="http://www.google.com">第四層選單有下層</a>
                        <ul>
                          <li><a href="#">第五層選單</a></li>
                          <li><a href="#">第五層選單</a></li>
                        </ul>
                      </li>
                      <li>
                        <a href="http://www.google.com">第四層選單有連結</a>
                      </li>
                      <li><a href="#">第四層選單</a></li>
                    </ul>
                  </li>
                  <li><a href="#">第三層選單</a></li>
                  <li><a href="#">第三層選單</a></li>
                </ul>
              </li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
          <li>
            <a href="#">第一層選單</a>
            <ul>
              <li><a href="#">第二層選單</a></li>
              <li>
                <a href="#">第二層選單</a>
                <ul>
                  <li>
                    <a href="http://www.google.com">第三層選單有下層</a>
                    <ul>
                      <li><a href="#">第四層選單</a></li>
                      <li><a href="#">第四層選單</a></li>
                    </ul>
                  </li>
                  <li>
                    <a href="http://www.google.com">第三層選單有連結</a>
                  </li>
                  <li><a href="#">第三層選單</a></li>
                </ul>
              </li>
              <li><a href="#">第二層選單</a></li>
              <li><a href="#">第二層選單</a></li>
            </ul>
          </li>
        </ul>
      </nav>
    </div>
  </div>
  <!-- menu End -->
</header>
```

<!-- tabs:end -->

<script>
function _jsParents(element, elementCheck) {
  const matched = [];

  const elements = typeof element === 'string' ? document.querySelectorAll(element) : element;

  // 取得每個元素的所有父節點，直到 <html>
  function _getParents(el) {
    while (el.parentNode && el.parentNode !== document.documentElement) {
      matched.push(el.parentNode);
      el = el.parentNode;
    }
  }

  // 處理集合與單一元素
  if (elements) {
    if (elements.length === undefined) {
      _getParents(elements);
    } else if (elements.nodeName !== 'SELECT') {
      elements.forEach(_getParents);
    }
  }

  // 根據 elementCheck 過濾父節點
  const filtered = matched.filter((parent) => {
    if (!elementCheck) {
      return true;
    } else if (elementCheck[0] === '#') {
      return parent.id === elementCheck.slice(1);
    } else if (elementCheck[0] === '.') {
      return parent.classList.contains(elementCheck.slice(1));
    } else if (typeof elementCheck === 'string') {
      return parent.localName === elementCheck.toLowerCase();
    } else {
      return parent === elementCheck;
    }
  });

  // 利用 Set 來進行去重複，並使用reverse()反轉順序
  return Array.from(new Set(filtered)).reverse();
}

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
}

// 改變標籤
// 改變標籤
function _changeTag(oldTag, newTag) {
  // 檢查 oldTag 是否存在於 DOM 中
  if (!oldTag || !oldTag.parentNode) return;

  const newTagElem = document.createElement(newTag);
  // 複製所有屬性
  for (const attr of oldTag.attributes) {
    newTagElem.setAttribute(attr.name, attr.value);
  }

  // 增加所有子節點
  while (oldTag.firstChild) {
    newTagElem.appendChild(oldTag.firstChild);
  }

  // 使用 replaceWith 替換舊標籤，語法更簡潔
  oldTag.replaceWith(newTagElem);
}

function _toggleDropdown(elem, con, autoClose = true) {
  const body = document.querySelector('body');
  const targetSelect = document.querySelector(elem);
  const targetSelectCon = document.querySelector(con);
  if (!targetSelectCon) return;

  if (!targetSelect) {
    targetSelectCon.style.display = 'block';
    return;
  }
  let checkDisplay = window.getComputedStyle(targetSelectCon).display === 'none';
  const id = `ts_${_randomLetter(3)}${_randomNumber(3)}`;

  if (checkDisplay) {
    targetSelect.setAttribute('aria-expanded', 'false');
  } else {
    targetSelect.setAttribute('aria-expanded', 'true');
    targetSelect.classList.add('active');
  }
  targetSelect.setAttribute('aria-haspopup', 'true');
  targetSelect.setAttribute('aria-controls', `${id}_con`);
  targetSelect.setAttribute('id', id);
  targetSelectCon.setAttribute('id', `${id}_con`);
  targetSelectCon.setAttribute('aria-labelledby', id);

  targetSelect.addEventListener('click', (e) => {
    let expanded = targetSelect.getAttribute('aria-expanded');
    expanded === 'true' ? closeCon() : openCon();
  });
  function openCon() {
    targetSelect.setAttribute('aria-expanded', 'true');
    targetSelect.classList.add('active');
    _jsSlideDown(targetSelectCon);
  }
  function closeCon() {
    targetSelect.setAttribute('aria-expanded', 'false');
    targetSelect.classList.remove('active');
    _jsSlideUp(targetSelectCon);
    targetSelect.focus();
  }
  body.addEventListener('keydown', (e) => {
    let allTarget = targetSelectCon.querySelectorAll('a, button, input, textarea, select');
    const firstTarget = allTarget[0];
    const lastTarget = [...allTarget].at(-1);

    if (targetSelect.getAttribute('aria-expanded') === 'true') {
      if (e.code === 'Tab') {
        if (e.target === targetSelect && e.shiftKey) {
          closeCon();
        } else if (e.target === firstTarget && e.shiftKey) {
          e.preventDefault();
          targetSelect.focus();
        } else if (e.target === lastTarget && !e.shiftKey) {
          e.preventDefault();
          closeCon();
        }
      }
      //Escape
      else if (e.code === 'Escape') {
        targetSelect.setAttribute('aria-expanded', 'false');
        _jsSlideUp(targetSelectCon);
        targetSelect.focus();
      }
    }
  });

  if (autoClose) {
    // 點擊其他地方關閉;
    body.addEventListener('click', (e) => {
      let isInsideTarget = _jsParents(e.target, targetSelectCon).length === 0;

      if (targetSelect.getAttribute('aria-expanded') === 'true' && e.target !== targetSelect && isInsideTarget) {
        targetSelect.setAttribute('aria-expanded', 'false');
        targetSelect.classList.remove('active');
        _jsSlideUp(targetSelectCon);
      }
    });
  }

  window.addEventListener('resize', (e) => {
    if (!checkDisplay) return;
    targetSelect.setAttribute('aria-expanded', 'false');
    targetSelect.classList.remove('active');
    _jsSlideUp(targetSelectCon);
  });
}


function mainMenu(obj) {
  // RWD切換判斷，與_variable.scss 的 --RWDWidth連動
  const setRWDWidth = parseInt(window.getComputedStyle(document.documentElement).getPropertyValue('--RWDWidth'));
  // 增加透明黑底
  let overlay = document.querySelector('.overlay');
  if (!overlay) {
    overlay = document.createElement('div');
    overlay.classList.add('overlay');
    document.body.insertAdjacentElement('afterbegin', overlay);
  }

  const body = document.querySelector('body');
  const header = document.querySelector('header');
  const headTop = document.querySelector('.headTop');
  const { sticky = true, needLink = false, mega = false } = obj;
  const mainMenu = document.querySelector('.mainMenu');
  if (mainMenu) {
    const menu = mainMenu.querySelector('nav');

    // 有下層的增加 hasChild 的 class
    const checkChild = menu.querySelectorAll('li ul');
    checkChild.forEach((item) => item.parentNode.classList.add('hasChild'));
  }
  // 檢查子選單是否超出視窗邊界
  function _checkBorder(e) {
    if (mega) return;
    // 抓出該項目以下有多少層級
    const nextUl = e.querySelectorAll('ul');
    //確定最後一層ul的父層li共有幾個
    const hasChildLi = _jsParents([...nextUl].at(-1), 'li');

    // 如果只有一層就不需要
    if (hasChildLi.length <= 1) return;

    // 確定選項的寬度 * 選項有幾層，由於第一層是直接向下不會左右展開，所以需要-1
    const checkUlWidth = hasChildLi[0].offsetWidth * hasChildLi.length - 1 || 0;

    //查詢第一層的位置
    const objectRect = hasChildLi[0].getBoundingClientRect();

    // 如果第一層左邊 + 其他層寬度超過視窗的寬度，則新增leftSlider
    if (window.outerWidth < objectRect.left + checkUlWidth) {
      hasChildLi[0].classList.add('leftSlider');
    } else {
      hasChildLi[0].classList.remove('leftSlider');
    }
  }

  // 滑鼠滑入
  function _handleMouseenter(e) {
    e.target.classList.add('active');
    e.target.querySelector('a').setAttribute('aria-expanded', 'true');
    _checkBorder(e.target);
  }

  // 滑鼠滑出
  function _handleMouseleave(e) {
    e.target.classList.remove('active');
    e.target.querySelector('a').setAttribute('aria-expanded', 'false');
    e.target.querySelector('ul').style.removeProperty('top');
  }

  // 選單層級展開fn
  function _toggleAccordion(item, con) {
    const nodeNameCheck = item.nodeName.toLowerCase();

    let content = item.parentNode.querySelector(con);
    if (window.getComputedStyle(content).display !== 'none') {
      item.setAttribute('aria-expanded', 'false');
      item.classList.remove('active');
    } else {
      item.setAttribute('aria-expanded', 'true');
      item.classList.add('active');
    }
    _jsSlideToggle(content);

    const siblings = [...item.parentNode.parentNode.children].filter((child) => child !== item.parentNode);

    siblings.forEach((j) => {
      if (j.querySelector(con)) {
        let target = j.querySelector(con);
        _jsSlideUp(target);
        j.querySelector(nodeNameCheck).setAttribute('aria-expanded', 'false');
      }
    });
  }

  // 桌面版選單初始化與事件綁定
  function _initDesktopMenu() {
    if (mainMenu) {
      const menu = mainMenu.querySelector('nav');
      const hasChild = menu.querySelectorAll('.hasChild');
      // 是否為megaMenu
      if (mega) {
        menu.classList.add('megaMenu');
        menu.classList.remove('menu');
        const megaMenuChild = menu.querySelectorAll(' ul ul .hasChild > a');
        megaMenuChild.forEach((i) => {
          i.removeAttribute('aria-haspopup');
        });
      }

      // 是否選單固定
      if (sticky) {
        const headerMargin = parseInt(window.getComputedStyle(header).marginBottom.replace('px', ''));

        window.addEventListener('scroll', function () {
          if (window.outerWidth > setRWDWidth) {
            if (headTop.clientHeight < window.scrollY) {
              header.classList.add('sticky');
              headTop.style.marginBottom = `${headerMargin + mainMenu.clientHeight}px`;
            } else {
              header.classList.remove('sticky');
              headTop.style.marginBottom = `${headerMargin}px`;
            }
          } else {
            headTop.removeAttribute('style');
          }
        });
      }

      // 使用事件委派處理滑鼠移入和移出事件
      menu.addEventListener(
        'mouseenter',
        (e) => {
          if (e.target.matches('.hasChild')) {
            _handleMouseenter(e);
          }
        },
        true
      );

      menu.addEventListener(
        'mouseleave',
        (e) => {
          if (e.target.matches('.hasChild')) {
            _handleMouseleave(e);
          }
        },
        true
      );

      //無障礙操作

      menu.addEventListener('keydown', (e) => {
        const checkHasSubmenu = e.target.parentNode.classList.contains('hasChild');
        const lastTarget = [...e.target.closest('ul').querySelectorAll('a,button,input,textarea,select')].at(-1);
        console.log(_jsParents(e.target, 'li'));

        _checkBorder(e.target.parentNode);
        if (window.outerWidth <= setRWDWidth) return;

        if (e.code === 'Tab' && !e.shiftKey) {
          const siblings = [...e.target.parentNode.parentNode.children].filter((child) => child !== e.target.parentNode);
          if (checkHasSubmenu) {
            e.target.parentNode.classList.add('active');
            e.target.setAttribute('aria-expanded', 'true');
          }
          siblings.forEach((j) => {
            j.classList.remove('active');
            j.classList.contains('hasChild') ? j.querySelector('a').setAttribute('aria-expanded', 'false') : null;
          });
          if (e.target === lastTarget) {
            _jsParents(e.target, 'li').forEach((j) => j.classList.remove('active'));
          }
        } else if (e.code === 'Tab' && e.shiftKey) {
          if (checkHasSubmenu) {
            e.target.parentNode.classList.remove('active');
            e.target.setAttribute('aria-expanded', 'false');
          }
        }
      });

      hasChild.forEach((i) => {
        const id = `menu_${_randomLetter(3)}${_randomNumber(3)}`;
        const childA = i.querySelector('a');
        const childUl = i.querySelector('ul');
        childA.setAttribute('aria-expanded', 'false');
        childA.setAttribute('aria-haspopup', 'true');
        childA.setAttribute('id', id);
        childA.setAttribute('aria-controls', `${id}_con`);
        childUl.setAttribute('id', `${id}_con`);
        childUl.setAttribute('aria-labelledby', id);
      });
    }
  }

  _initDesktopMenu();

  // 手機版選單初始化與事件綁定
  function _initMobileMenu() {
    const header = document.querySelector('header');
    const mobileMenu = document.createElement('nav');
    mobileMenu.setAttribute('id', 'mobileMenu');
    mobileMenu.setAttribute('aria-labelledby', 'mobileMainMenuBtn');

    // 新增手機版主選單容器
    const mobileMainMenuBox = document.createElement('div');
    mobileMainMenuBox.classList.add('mobileMainMenuBox');

    // 複製主選單
    if (mainMenu) {
      const menu = mainMenu.querySelector('nav');
      const mainMenuClone = menu.cloneNode(true);
      mainMenuClone.classList.remove('mainMenu', 'menu');
      mainMenuClone.classList.add('mobileMainMenu');
      // 將 主選單 加入到 手機版主選單
      mobileMainMenuBox.insertAdjacentElement('afterbegin', mainMenuClone);

      // 轉換標籤
      _changeTag(mainMenuClone, 'div');
    }

    // 複製top選單
    const topNav = document.querySelector('.topNav');
    if (topNav) {
      const topNavClone = topNav.cloneNode(true);

      topNavClone.querySelector('.fontSize')?.remove();
      topNavClone.querySelector('.topSearch')?.remove();
      topNavClone.querySelector('#aU')?.remove();
      // 將 top選單 加入到 手機版主選單
      mobileMainMenuBox.insertAdjacentElement('beforeend', topNavClone);
      _changeTag(topNavClone, 'div');
    }

    // 將 手機版主選單 加入到 手機版主選單(多包一層div)
    mobileMenu.insertAdjacentElement('afterbegin', mobileMainMenuBox);
    // 將 手機版主選單 加入到 header 前
    header?.insertAdjacentElement('beforebegin', mobileMenu);

    // 點擊選單按鈕 執行 展開側邊選單函式
    const mobileMainMenuBtn = document.querySelector('#mobileMainMenuBtn');
    mobileMainMenuBtn.setAttribute('aria-controls', 'mobileMenu');
    mobileMainMenuBtn.setAttribute('aria-expanded', 'false');
    mobileMainMenuBtn.setAttribute('aria-pressed', 'false');
    mobileMainMenuBtn.setAttribute('aria-haspopup', 'true');

    // 展開側邊選單函式
    function _showSidebar() {
      mobileMenu.style.opacity = '1';
      mobileMenu.style.display = 'block';
      mobileMainMenuBtn.setAttribute('aria-expanded', 'true');
      mobileMainMenuBtn.setAttribute('aria-pressed', 'true');

      setTimeout(() => {
        mobileMenu.style.transform = 'translateX(0px)';
        mobileMenu.classList.add('open');
      }, 0);
      mobileMainMenuBtn.classList.add('active');
      if (window.outerWidth < setRWDWidth) body.classList.add('noscroll');
      _jsFadeIn(overlay);
      overlay.style.zIndex = '90';
    }

    // 隱藏側邊選單函式
    function _hideSidebar(overlayFN = true) {
      mobileMenu.style.transform = 'translateX(-100%)';
      mobileMainMenuBtn.setAttribute('aria-expanded', 'false');
      mobileMainMenuBtn.setAttribute('aria-pressed', 'false');

      // 等待 300ms 的動畫時間
      setTimeout(() => {
        mobileMenu.removeAttribute('style');
      }, 300);

      mobileMenu.classList.remove('open');
      body.classList.remove('noscroll');
      mobileMainMenuBtn.classList.remove('active');
      overlay.style.zIndex = '';
      if (overlayFN) _jsFadeOut(overlay);
    }

    mobileMainMenuBtn.addEventListener('click', (e) => {
      e.preventDefault();
      if (mobileMainMenuBtn.getAttribute('aria-expanded') === 'true') {
        _hideSidebar();
      } else {
        _showSidebar();
      }
      mobileMainMenuBtn.focus();
    });

    overlay.addEventListener('click', () => _hideSidebar());

    // 使用事件委派處理手機選單的點擊事件
    mobileMenu.addEventListener('click', (e) => {
      const target = e.target;
      const hasChildLi = target.closest('.hasChild');

      if (hasChildLi) {
        let childControl;
        if (!needLink) {
          childControl = hasChildLi.querySelector('a');
          if (target === childControl) {
            e.preventDefault();
            _toggleAccordion(childControl, 'ul');
          }
        } else {
          childControl = hasChildLi.querySelector('.nextLvl');
          if (target === childControl) {
            _toggleAccordion(childControl, 'ul');
          }
        }
      }
    });

    // 初始設定
    const mobileMenuLiHasChild = mobileMenu.querySelectorAll('li.hasChild');
    mobileMenuLiHasChild.forEach((i) => {
      let childControl;
      if (!needLink) {
        childControl = i.querySelector('a');
        childControl.setAttribute('role', 'button');
      } else {
        i.classList.add('needLink');
        const nextA = i.querySelector('a');
        const nextBtn = document.createElement('button');
        nextBtn.classList.add('nextLvl');
        nextA.insertAdjacentElement('afterend', nextBtn);
        nextBtn.setAttribute('id', nextA.getAttribute('id'));
        childControl = nextBtn;
      }

      // 無障礙設定 -- mobile
      const id = `mobileMenu_${_randomLetter(3)}${_randomNumber(3)}`;
      const childUl = i.querySelector('ul');
      childControl.setAttribute('aria-expanded', 'false');
      childControl.setAttribute('aria-haspopup', 'true');
      childControl.setAttribute('id', id);
      childControl.setAttribute('aria-controls', `${id}_con`);
      childUl.setAttribute('id', `${id}_con`);
      childUl.setAttribute('aria-labelledby', id);
    });

    // 手機版鍵盤無障礙設定
    const allMobileMenuTarget = mobileMenu.querySelectorAll('a,button,input,select');
    body.addEventListener('keydown', (e) => {
      if (e.code === 'Escape' && mobileMainMenuBtn.getAttribute('aria-expanded') === 'true') {
        _hideSidebar();
      } else if (e.code === 'Tab' && !e.shiftKey && e.target === mobileMainMenuBtn && mobileMainMenuBtn.getAttribute('aria-expanded') === 'true') {
        e.preventDefault();
        allMobileMenuTarget[0].focus();
      } else if (e.code === 'Tab' && e.shiftKey && e.target === allMobileMenuTarget[0]) {
        e.preventDefault();
        mobileMainMenuBtn.focus();
      }
    });

    window.addEventListener('resize', function () {
      if (window.outerWidth <= setRWDWidth) {
        headTop.removeAttribute('style');
      } else {
        body.classList.remove('noscroll');
        _hideSidebar();
      }
    });
    const mobileSearchBtn = document.querySelector('#mobileSearchBtn');
    if (!mobileSearchBtn) return;
    mobileSearchBtn.addEventListener('click', () => _hideSidebar(false));
  }
  _initMobileMenu();
}



  _toggleDropdown('.subNavList .fontSize > button', '.subNavList .fontSize ul'); //文字大小展開開關切換
  _toggleDropdown('.navList .fontSize > button', '.navList .fontSize ul'); //文字大小展開開關切換
  _toggleDropdown('header .subNavList .language > button', 'header .subNavList .language ul'); //語系開關切換
  _toggleDropdown('header .navList .language > button', 'header .navList .language ul'); //語系開關切換
  mainMenu({
  sticky: false, // 是否置頂
  mega: false, // 是否megaMenu
  needLink: false, // 如果同時需要連結和下層功能時(手機版選單)
});
</script>
