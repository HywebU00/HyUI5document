# Search 搜尋

?>相關 css：相關 css：scss/components/`_search.scss`

網頁搜尋區塊預設是需要點選按鈕後才會展開搜尋區塊，若需要直接顯示搜尋區塊，只需要把`topNav`中`topSearch 按鈕`元件移除即會直接顯示。

**範例**

<header style="position:relative;">
<nav class="topNav" role="navigation" aria-label="頁首功能列">
  <div class="subNavList">
<div class="topSearch sliderFn">
  <button id="topSearchBtn" type="button">網站搜尋</button>
</div></div>
</nav>
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
</header>

<!-- tabs:start -->

#### **HTML**

```html
<nav class="topNav" role="navigation" aria-label="頁首功能列">
  <div class="subNavList">
    <!-- topSearch 按鈕 Start -->
    <div class="topSearch sliderFn">
      <button id="topSearchBtn" type="button">網站搜尋</button>
    </div>
    <!-- topSearch 按鈕 ENd -->
  </div>
</nav>

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
```

<!-- tabs:end -->

<style>
  header{
    max-width:415px;
  }
.topNav{
justify-content: flex-start !important;
}
</style>

<script>
function _jsSlideDown(element, time = 200) {
  let ele = window.getComputedStyle(element);
  let display = ele.display;
  let speed = time;
  element.style.display = display;
  if (display === 'none') {
    element.style.display = 'block';
    element.style.overflow = 'hidden';
    let totalHeight = element.offsetHeight;
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
  }
}
function _jsSlideUp(element, time = 200) {
  let ele = window.getComputedStyle(element);
  let display = ele.display;
  let speed = time;
  element.style.display = display;
  if (display !== 'none') {
    let totalHeight = element.offsetHeight;
    element.style.overflow = 'hidden';

    element.style.height = `${totalHeight}px`;
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


  function webSearch() {
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
  const webSearch = document.querySelector('.webSearch');

  if (!webSearch) return;
  // console.warn('網站搜尋功能: webSearch 無法抓到(請檢查Html結構)，或是沒有使用到此功能');
  // return;

  const mobileSearchBtn = document.querySelector('#mobileSearchBtn');
  const webSearchBtn = document.querySelector('#topSearchBtn');
  const searchTargetSelect = document.querySelectorAll('#topSearchBtn, #mobileSearchBtn');
  const webSearchAllTarget = webSearch.querySelectorAll('a, button, input, select, textarea');
  const id = `ws_${_randomLetter(3)}${_randomNumber(3)}`;

  if (webSearchBtn) {
    // 桌機搜尋按鈕進行設定與事件綁定
    webSearchBtn.setAttribute('aria-controls', `${id}_con`);
    webSearchBtn.setAttribute('aria-expanded', 'false');
    webSearchBtn.setAttribute('aria-pressed', 'false');
    webSearchBtn.setAttribute('aria-haspopup', 'true');
    webSearchBtn.addEventListener('click', () => _toggleContent(webSearchBtn));
  }

  // 行動版搜尋按鈕設定及事件綁定
  if (mobileSearchBtn) {
    mobileSearchBtn.setAttribute('aria-controls', `${id}_con`);
    mobileSearchBtn.setAttribute('aria-expanded', 'false');
    mobileSearchBtn.setAttribute('aria-pressed', 'false');
    mobileSearchBtn.setAttribute('aria-haspopup', 'true');
    mobileSearchBtn.addEventListener('click', () => _toggleContent(mobileSearchBtn));
  }

  // 搜尋內容區塊設定 ARIA 標記，建立與觸發按鈕的關聯
  webSearch.setAttribute('id', `${id}_con`);
  webSearch.setAttribute('aria-labelledby', `topSearchBtn mobileSearchBtn`);

  //  切換搜尋展開/關閉的函式
  function _toggleContent(elem) {
    const checkDisplay = window.getComputedStyle(webSearch).display === 'none';

    if (checkDisplay) {
      _showSearchBox(elem);
      if (window.outerWidth < setRWDWidth) body.classList.add('noscroll');
    } else {
      _hideSearchBox(elem);
      body.classList.remove('noscroll');
    }
  }

  function _showSearchBox(elem) {
    elem?.setAttribute('aria-expanded', 'true');
    elem?.setAttribute('aria-pressed', 'true');
    elem?.classList.add('active');
    // 清空搜尋區塊內第一個可編輯項目的值（例如輸入框）
    setTimeout(() => {
      if (webSearchAllTarget[0]) webSearchAllTarget[0].value = '';
      if (webSearchAllTarget[0]) webSearchAllTarget[0].focus();
    });
    _jsSlideDown(webSearch);
    window.outerWidth < setRWDWidth ? _jsFadeIn(overlay) : null;
  }

  function _hideSearchBox(elem, overLayFn = true) {
    elem.setAttribute('aria-expanded', 'false');
    elem.setAttribute('aria-pressed', 'false');
    elem.classList.remove('active');
    _jsSlideUp(webSearch);

    if (overLayFn) {
      _jsFadeOut(overlay);
      setTimeout(() => {
        elem.focus();
      });
    }
  }

  // 鍵盤事件設定，支援 Tab、Enter、Alt+S 快捷鍵以及 Escape 關閉
  body.addEventListener('keydown', (e) => {
    const isSearchBtn = e.target === webSearchBtn || e.target === mobileSearchBtn;
    const searchBtn = window.outerWidth >= setRWDWidth ? webSearchBtn : mobileSearchBtn;
    const lastTarget = [...webSearchAllTarget].at(-1);

    // Tab
    if (e.code === 'Tab') {
      if (e.target === lastTarget) {
        _toggleContent(searchBtn);
      }
      if (e.shiftKey && isSearchBtn) {
        const checkDisplay = window.getComputedStyle(webSearch).display === 'none';
        !checkDisplay ? _hideSearchBox(searchBtn, true) : null;
      }
      // Alt+S
    } else if (e.altKey && e.code === 'KeyS') {
      _toggleContent(searchBtn);

      // Escape
    } else if (e.code === 'Escape') {
      const checkDisplay = window.getComputedStyle(webSearch).display;
      if (checkDisplay === 'none') return;
      if (window.outerWidth >= setRWDWidth && webSearchBtn) {
        _toggleContent(webSearchBtn);
      } else if (window.outerWidth < setRWDWidth && mobileSearchBtn) {
        _toggleContent(mobileSearchBtn);
      }
      _jsFadeOut(overlay);
    }
  });

  // 點擊其他地方時關閉搜尋面板
  body.addEventListener('click', (e) => {
    const isInsideSearch = _jsParents(e.target, webSearch).length === 0;

    searchTargetSelect.forEach((item) => {
      if (item.getAttribute('aria-expanded') === 'true' && e.target !== item && isInsideSearch && webSearchBtn !== null) {
        item.setAttribute('aria-expanded', 'false');
        item.setAttribute('aria-pressed', 'false');
        item.classList.remove('active');
        _jsSlideUp(webSearch);
        _jsFadeOut(overlay);
      }
    });
  });
  const mobileMainMenuBtn = document.querySelector('#mobileMainMenuBtn');
  if (!mobileMainMenuBtn) return;
  mobileMainMenuBtn.addEventListener('click', () => _hideSearchBox(mobileSearchBtn, false));
}
window.addEventListener('load', () => webSearch());
</script>
