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
      <a href="#"><img src="images/basic/icon/share/facebook.svg" alt="facebook" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/youtube.svg" alt="youtube" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/x.svg" alt="x" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/instagram.svg" alt="instagram" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/email.svg" alt="email" /></a>
    </li>
  </ul>
  <button class="floatSwitchBtn" aria-label="開關悬浮按鈕"></button>
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
      <a href="#"><img src="images/basic/icon/share/facebook.svg" alt="facebook" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/youtube.svg" alt="youtube" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/x.svg" alt="x" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/instagram.svg" alt="instagram" /></a>
    </li>
    <li>
      <a href="#"><img src="images/basic/icon/share/email.svg" alt="email" /></a>
    </li>
  </ul>
  <button class="floatSwitchBtn" aria-label="開關悬浮按鈕"></button>
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
}function _jsParents(element, elementCheck) {
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
  _toggleDropdown('.floatNav .floatSwitchBtn', '.floatNav .typeA'); //LP 內容搜尋
</script>
