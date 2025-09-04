# Accordion 收合式選單

?>相關 css：scss/components/`_accordion.scss`

點擊 `accordionBtn`，來顯示及隱藏另一個元素，點擊後 `accordionList`增加`active` 可自由設定 css 樣式。

說明文字(展開/收合)從`accordion`中抓取，方便多語系修改。

- **data-state-open="展開"**  
  收合時顯示的說明文字
- **data-state-close="收合"**  
  展開時顯示的說明文字

**範例**

<div class="accordion" data-state-open="展開" data-state-close="收合">
  <div class="accordionList">
    <button class="accordionBtn">第一項說明</button>
    <div class="accordionContent">
      <div class="content">
        無障礙相關(皆已由js設定)
        <ul>
          <li>
            <a href="#">按鈕</a>
            <ol>
              <li>展開的按鈕項加<code>aria-expanded="true"</code>，未展開的按鈕項加<code>aria-expanded="false"</code></li>
            </ol>
          </li>
          <li>
            <a href="#">內容</a>
            <ol>
              <li>內容加上<code>role="region"</code></li>
              <li>展開的加上<code>aria-hidden="false"</code>，未展開的加上<code>aria-hidden="true"</code></li>
            </ol>
          </li>
          <li>
            <a href="#">讓按鈕項與按鈕內容產生關連</a>
            <ol>
              <li>頁籤加<code>id="<i>ID</i>"</code>，對應的內容加<code>aria-labelledby="<i>ID</i>"</code><br />例如，第一個頁籤項<code>id="tabpanel_1"</code>，其控制的內容<code>aria-labelledby="tabpanel_1"</code></li>
              <li>內容區加<code>id="<i>ID</i>"</code>，對應的頁籤項加<code>aria-controls="<i>ID</i>"</code><br />例如，第一個頁籤項<code>aria-controls="tabpanel_1_con"</code>，其控制的內容<code>id="tabpanel_1_con"</code></li>
            </ol>
          </li>
        </ul>
      </div>
    </div>
  </div>
  <div class="accordionList">
    <button class="accordionBtn" title="">第二項說明</button>
    <div class="accordionContent">
      <div class="content">
        國影自談王不美一文實別合屋？府性元這子一知於料的親到。一用技年不得就資公，也星樣團怎英班水灣個種決以因世書發定很功行何，下飯通反代命假到一不離護麼錯絕懷旅元人。弟新過，道給仍覺裡水國、醫灣了可實界一上德字什心成但創大品隨品。<br />
        <a href="#">連結</a>
        <a href="#">連結</a>
      </div>
    </div>
  </div>
  <div class="accordionList">
    <button class="accordionBtn" title="">第三項說明</button>
    <div class="accordionContent">
      <div class="content">
        國影自談王不美一文實別合屋？府性元這子一知於料的親到。一用技年不得就資公，也星樣團怎英班水灣個種決以因世書發定很功行何，下飯通反代命假到一不離護麼錯絕懷旅元人。弟新過，道給仍覺裡水國、醫灣了可實界一上德字什心成但創大品隨品。<br />
        <a href="#">連結</a>
        <a href="#">連結</a>
      </div>
    </div>
  </div>
  <div class="accordionList">
    <button class="accordionBtn" title="">第四項說明</button>
    <div class="accordionContent">
      <div class="content">
        國影自談王不美一文實別合屋？府性元這子一知於料的親到。一用技年不得就資公，也星樣團怎英班水灣個種決以因世書發定很功行何，下飯通反代命假到一不離護麼錯絕懷旅元人。弟新過，道給仍覺裡水國、醫灣了可實界一上德字什心成但創大品隨品。<br />
        <a href="#">連結</a>
        <a href="#">連結</a>
      </div>
    </div>
  </div>
</div>

<!-- tabs:start -->

### **HTML**

```html
<div class="accordion" data-state-open="展開" data-state-close="收合">
  <div class="accordionList">
    <button class="accordionBtn">第一項說明</button>
    <div class="accordionContent">
      <div class="content"></div>
    </div>
  </div>
  <div class="accordionList">
    <button class="accordionBtn" title="">第二項說明</button>
    <div class="accordionContent">
      <div class="content"></div>
    </div>
  </div>
  <div class="accordionList">
    <button class="accordionBtn" title="">第三項說明</button>
    <div class="accordionContent">
      <div class="content"></div>
    </div>
  </div>
  <div class="accordionList">
    <button class="accordionBtn" title="">第四項說明</button>
    <div class="accordionContent">
      <div class="content"></div>
    </div>
  </div>
</div>
```

### **JS**

```javascript
// option是基礎預設，如不需要更改可以直接使用
// accordionFunction('.target')，如有多組accordion請另外設定target
accordionFunction({
  target: '.accordion',
  openContent: false, // 預設先展開所有內容
  openDefault: true, // 是否有預設開啟
  openIndex: 0, // 預設開啟第幾個
  autoClose: true, // 自動關閉其他開啟內容
  openSwitch: true, // 是否可開合/切換
});
```

<!-- tabs:end -->

<style>
  .accordion .content{
    position:relative !important;
    left:auto !important;
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
function _jsSlideToggle(element, time = 200) {
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
function accordionFunction(obj) {
  const { target, openContent = false, openDefault = false, autoClose = true, openSwitch = true } = obj;

  const accordionSet = document.querySelector(target);
  if (!accordionSet) return;
  // console.warn('手風琴功能: accordionSet 無法抓到(請檢查Html結構)，或是沒有使用到此功能');
  // return;

  const infoOpen = accordionSet.dataset.stateOpen;
  const infoClose = accordionSet.dataset.stateClose;
  const accordionList = accordionSet.querySelectorAll('.accordionList');
  const accordionBtns = accordionSet.querySelectorAll('.accordionBtn');
  const accordionCons = accordionSet.querySelectorAll('.accordionContent');
  const defaultIndex = [...accordionList].indexOf(accordionSet.querySelector('.active')) === -1 ? 0 : [...accordionList].indexOf(accordionSet.querySelector('.active'));

  //初始設定
  function _accordionInit() {
    accordionBtns.forEach((accordion, i) => {
      const id = `accordion_${_randomLetter(3)}${_randomNumber(3)}`;
      const controls = `${id}_con`;

      // 增加展開說明文字
      let accordionStateOuter;
      let accordionState;
      if (openSwitch) {
        let accordionStateOuter = document.createElement('div');
        accordionState = document.createElement('span');
        accordionStateOuter.classList.add('accordionState');
        accordionState.insertAdjacentHTML('afterbegin', infoOpen);
        accordionStateOuter.insertAdjacentElement('beforeend', accordionState);
        accordion.insertAdjacentElement('beforeend', accordionStateOuter);
      }

      //button
      accordion.setAttribute('id', id);
      accordion.setAttribute('aria-controls', controls);
      accordion.setAttribute('aria-expanded', 'false');

      //content
      accordionCons[i].setAttribute('id', controls);
      accordionCons[i].setAttribute('aria-labelledby', id);
      accordionCons[i].setAttribute('role', 'region');

      if (openContent) {
        // 預設先展開所有內容
        accordion.classList.add('active');
        accordion.setAttribute('aria-expanded', 'true');
        if (openSwitch) accordionState.textContent = infoClose;
      } else if (!openContent) {
        accordion.setAttribute('aria-expanded', 'false');
        accordionCons[i].style.display = 'none';
      }
    });

    if (openDefault) {
      accordionBtns[defaultIndex].parentElement.classList.add('active');
      accordionBtns[defaultIndex].setAttribute('aria-expanded', 'true');
      _jsSlideDown(accordionCons[defaultIndex]);
      if (openSwitch) accordionBtns[defaultIndex].querySelector('.accordionState span').textContent = infoClose;
    }
  }
  _accordionInit();

  function _accordionFn(btn, i) {
    const accordionState = btn.querySelector('.accordionState span');
    _jsSlideToggle(accordionCons[i]);
    accordionSet.dataset.nowIndex = i;
    let infoText = accordionState.textContent === infoClose ? infoOpen : infoClose;
    let expanded = btn.getAttribute('aria-expanded') === 'true' ? false : true;
    accordionState.textContent = infoText;
    btn.setAttribute('aria-expanded', expanded);
    btn.parentElement.classList.toggle('active');

    if (!autoClose) return;
    const siblingsMobileAccordionBtns = [...accordionBtns].filter((value) => value !== accordionBtns[i]);
    siblingsMobileAccordionBtns.forEach((value) => {
      value.parentElement.classList.remove('active');
      value.querySelector('.accordionState span').textContent = infoOpen;
    });
    const siblingsAccordionCons = [...accordionCons].filter((value) => value !== accordionCons[i]);
    siblingsAccordionCons.forEach((value) => _jsSlideUp(value));
    setTimeout(() => {
      let btnClientRect = btn.getBoundingClientRect();
      if (btnClientRect.y < 0) {
        window.scrollTo({
          top: window.scrollY + btnClientRect.y - btnClientRect.height - 20,
          behavior: 'smooth',
        });
      }
    }, 200);
  }

  // 是否可開合/切換
  if (openSwitch) {
    accordionBtns.forEach((btn, i) => {
      btn.addEventListener('click', (e) => {
        e.preventDefault();
        _accordionFn(btn, i);
      });
    });
  }
}

accordionFunction({
  target: '.accordion',
  openContent: false, // 預設先展開所有內容
  openDefault: true, // 是否有預設開啟
  openIndex: 0, // 預設開啟第幾個
  autoClose: true, // 自動關閉其他開啟內容
  openSwitch: true, // 是否可開合/切換
});
</script>
