# Tabs / 頁籤

?>相關 css：scss/components/`tabs.scss`

提供一組**可響應式及通過無障礙** tab 遊走之 tab 頁籤模組。

- 頁籤沒有數量限制，但請注意畫面上的均衡比例。建議勿超過 5 組為宜。
- 可客製不同樣式，於`tabs`後方新增不同的 `classnName`即可。>
- 可自訂響應式斷點(Breakpoints)，如有 特殊需求，可另外替換變數或數值。

<div class="tabSet tabFunction1">
  <div class="tabBtnBox">
    <div class="tabItems">
      <button type="button" class="tabBtn"><span>頁籤項ㄧ</span></button>
      <button type="button" class="tabBtn active">頁籤項二</button>
      <button type="button" class="tabBtn">頁籤項三</button>
      <button type="button" class="tabBtn">頁籤項四</button>
      <button type="button" class="tabBtn">頁籤項五</button>
    </div>
  </div>
  <div class="tabContentGroup">
    <div class="tabContent">
      <div class="tabContentIn">
        tabFunction({<br />
        target: '.target1', // 執行目標，多組需要另外設定<br />
        modeSwitch: false, // 自動切換，尺寸以上tab功能，尺寸以下手風琴功能<br />
        openContent: false, // 展開所有內容，僅開啟模式切換時才可使用<br />
        width: 767, // 尺寸以上tab功能，尺寸以下手風琴功能<br />
        autoClose: true, // 自動關閉其他開啟內容<br />
        openSwitch: true, // 是否可開合/切換<br />
        });<br />
        上面的option是基礎預設，如不需要更改可以直接使用tabFunction('.target1')，如有多組tab<br />
        預設第幾個開啟在按鈕上設定class active即<br /><br />
        請另外設定target <br /><br />
        無障礙相關(皆已由js設定)
        <ul>
          <li>
            <a href="#">頁籤</a>
            <ol>
              <li>父層增加role="tablist"</li>
              <li>&lt;button&gt;加上role="tab"</li>
            </ol>
          </li>
          <li>
            <a href="#">內容</a>
            <ol>
              <li>&lt;button&gt;加上role="tabpanel"</li>
            </ol>
          </li>
          <li>
            <a href="#">讓頁籤項與頁籤內容產生關連</a>
            <ol>
              <li>頁籤加id="<i>ID</i>"，對應的內容加aria-labelledby="<i>ID</i>"<br />例如，第一個頁籤項id="tabpanel_1"，其控制的內容aria-labelledby="tabpanel_1"</li>
              <li>內容區加id="<i>ID</i>"，對應的頁籤項加aria-controls="<i>ID</i>"<br />例如，第一個頁籤項aria-controls="tabpanel_1_con"，其控制的內容id="tabpanel_1_con"</li>
            </ol>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        2
        <ul>
          <li>
            <a href="#">頁籤二內容</a>
          </li>
          <li>
            <a href="#">人運部界政那我金後北製？差藥當兩；面下推的從不票她走子文內另來一得</a>
          </li>
          <li>
            <a href="#">機子年安才生家更前陽象望土福開人道高投了初幾的我辦量部念地中是基</a>
          </li>
          <li>
            <a href="#">只利她遊是態遠他大久呢來皮研，來三了裡後半物國檢。</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        3 標題：探索未知的世界<br /><br />
        引言<br />
        在這個充滿奇遇和冒險的世界裡，我們常常被吸引到未知的領域中。這些未知的領域充滿了神秘和挑戰，讓我們感到興奮和好奇。本文將帶領您一同探索這些未知的領域，揭開它們的神秘面紗。<br /><br />
        第一章：神奇的自然界<br />
        自然界是一個充滿驚喜和美妙的地方。無論是壯麗的山脈、湛藍的海洋還是多彩的花草，都讓人讚嘆不已。而在這個世界的角落，還有許多未知的生物和現象等待我們去發現。例如，深海中的生物群落、古老的森林中的神秘生物，以及空中飄浮的奇特現象，都是我們可以探索的寶藏。<br /><br />
        第二章：科技的奇跡<br />
        科技的發展讓我們能夠窺探到更多未知的領域。例如，人工智能的進步讓我們能夠模擬和理解人腦中的神秘運作；太空探索的成果讓我們能夠窺探宇宙的奧秘。這些科技的奇跡不僅擴大了我們的知識範圍，也為我們帶來了更多的可能性。<br /><br />
        第三章：藝術的魅力<br />
        藝術是人類創造力的結晶，同樣也是一個充滿未知的領域。藝術家們通過他們的創作，探索和表達人類情感和思想。他們使用不同的媒介和技巧，創造出無盡的可能性。每一幅畫作、每一首音樂、每一部電影都是一個獨特的世界，等待我們去發現和欣賞。<br /><br />
        總結<br />
        在這個充滿未知的世界中，我們不斷地探索、學習和成長。無論是自然界、科技還是藝術，都是我們探索未知的途徑。讓我們保持好奇心和求知慾，勇敢地踏上未知的旅程
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        4
        <ul>
          <li>
            <a href="#">頁籤三內容</a>
          </li>
          <li>
            <a href="#">頁籤三內容</a>
          </li>
          <li>
            <a href="#">林人還是答以學領進保後錢愛而營，母石時以是養人年！</a>
          </li>
          <li>
            <a href="#">獲親應歌治前方相分之被參大治打地國許聲引會賣試萬只只業臺做不什北反照人機止了造人企！</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        5
        <ul>
          <li>
            <a href="#">頁籤四內容</a>
          </li>
          <li>
            <a href="#">天一己有門起下模大且只身民家三歌先媽斯率高觀我張高看經。</a>
          </li>
          <li>
            <a href="#">上總簡能主意無百過可們的不來。</a>
          </li>
          <li>
            <a href="#">早進立研最題，滿微升我以我麗什綠是手時國聽感他球明定</a>
          </li>
          <li>
            <a href="#">步第完出著興就年題樣程用是著則分除到手人件些策不制爭人。 </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</div>
<!-- tabs:start -->

#### **HTML**

```html
<div class="tabSet tabFunction1">
  <div class="tabBtnBox">
    <div class="tabItems">
      <button type="button" class="tabBtn"><span>頁籤項ㄧ</span></button>
      <button type="button" class="tabBtn active">頁籤項二</button>
      <button type="button" class="tabBtn">頁籤項三</button>
      <button type="button" class="tabBtn">頁籤項四</button>
      <button type="button" class="tabBtn">頁籤項五</button>
    </div>
  </div>
  <div class="tabContentGroup">
    <div class="tabContent">
      <div class="tabContentIn">
        tabFunction({<br />
        target: '.target1', // 執行目標，多組需要另外設定<br />
        modeSwitch: false, // 自動切換，尺寸以上tab功能，尺寸以下手風琴功能<br />
        openContent: false, // 展開所有內容，僅開啟模式切換時才可使用<br />
        width: 767, // 尺寸以上tab功能，尺寸以下手風琴功能<br />
        autoClose: true, // 自動關閉其他開啟內容<br />
        openSwitch: true, // 是否可開合/切換<br />
        });<br />
        上面的option是基礎預設，如不需要更改可以直接使用tabFunction('.target1')，如有多組tab<br />
        預設第幾個開啟在按鈕上設定class active即<br /><br />
        請另外設定target <br /><br />
        無障礙相關(皆已由js設定)

        <ul>
          <li>
            <a href="#">頁籤</a>
            <ol>
              <li>父層增加role="tablist"</li>
              <li>&lt;button&gt;加上role="tab"</li>
            </ol>
          </li>
          <li>
            <a href="#">內容</a>
            <ol>
              <li>&lt;button&gt;加上role="tabpanel"</li>
            </ol>
          </li>
          <li>
            <a href="#">讓頁籤項與頁籤內容產生關連</a>
            <ol>
              <li>頁籤加id="<i>ID</i>"，對應的內容加aria-labelledby="<i>ID</i>"<br />例如，第一個頁籤項id="tabpanel_1"，其控制的內容aria-labelledby="tabpanel_1"</li>
              <li>內容區加id="<i>ID</i>"，對應的頁籤項加aria-controls="<i>ID</i>"<br />例如，第一個頁籤項aria-controls="tabpanel_1_con"，其控制的內容id="tabpanel_1_con"</li>
            </ol>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        2
        <ul>
          <li>
            <a href="#">頁籤二內容</a>
          </li>
          <li>
            <a href="#">人運部界政那我金後北製？差藥當兩；面下推的從不票她走子文內另來一得</a>
          </li>
          <li>
            <a href="#">機子年安才生家更前陽象望土福開人道高投了初幾的我辦量部念地中是基</a>
          </li>
          <li>
            <a href="#">只利她遊是態遠他大久呢來皮研，來三了裡後半物國檢。</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        3 標題：探索未知的世界<br /><br />
        引言<br />
        在這個充滿奇遇和冒險的世界裡，我們常常被吸引到未知的領域中。這些未知的領域充滿了神秘和挑戰，讓我們感到興奮和好奇。本文將帶領您一同探索這些未知的領域，揭開它們的神秘面紗。<br /><br />

        第一章：神奇的自然界<br />
        自然界是一個充滿驚喜和美妙的地方。無論是壯麗的山脈、湛藍的海洋還是多彩的花草，都讓人讚嘆不已。而在這個世界的角落，還有許多未知的生物和現象等待我們去發現。例如，深海中的生物群落、古老的森林中的神秘生物，以及空中飄浮的奇特現象，都是我們可以探索的寶藏。<br /><br />

        第二章：科技的奇跡<br />
        科技的發展讓我們能夠窺探到更多未知的領域。例如，人工智能的進步讓我們能夠模擬和理解人腦中的神秘運作；太空探索的成果讓我們能夠窺探宇宙的奧秘。這些科技的奇跡不僅擴大了我們的知識範圍，也為我們帶來了更多的可能性。<br /><br />

        第三章：藝術的魅力<br />
        藝術是人類創造力的結晶，同樣也是一個充滿未知的領域。藝術家們通過他們的創作，探索和表達人類情感和思想。他們使用不同的媒介和技巧，創造出無盡的可能性。每一幅畫作、每一首音樂、每一部電影都是一個獨特的世界，等待我們去發現和欣賞。<br /><br />

        總結<br />
        在這個充滿未知的世界中，我們不斷地探索、學習和成長。無論是自然界、科技還是藝術，都是我們探索未知的途徑。讓我們保持好奇心和求知慾，勇敢地踏上未知的旅程
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        4
        <ul>
          <li>
            <a href="#">頁籤三內容</a>
          </li>
          <li>
            <a href="#">頁籤三內容</a>
          </li>
          <li>
            <a href="#">林人還是答以學領進保後錢愛而營，母石時以是養人年！</a>
          </li>
          <li>
            <a href="#">獲親應歌治前方相分之被參大治打地國許聲引會賣試萬只只業臺做不什北反照人機止了造人企！</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabContent" role="tabpanel">
      <div class="tabContentIn">
        5
        <ul>
          <li>
            <a href="#">頁籤四內容</a>
          </li>
          <li>
            <a href="#">天一己有門起下模大且只身民家三歌先媽斯率高觀我張高看經。</a>
          </li>
          <li>
            <a href="#">上總簡能主意無百過可們的不來。</a>
          </li>
          <li>
            <a href="#">早進立研最題，滿微升我以我麗什綠是手時國聽感他球明定</a>
          </li>
          <li>
            <a href="#">步第完出著興就年題樣程用是著則分除到手人件些策不制爭人。 </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</div>
```

#### **JS**

```javascript
tabFunction({
  target: '.target1', // 執行目標，多組需要另外設定
  modeSwitch: false, // 自動切換，尺寸以上tab功能，尺寸以下手風琴功能
  openContent: false, // 展開所有內容，僅開啟模式切換時才可使用
  openIndex: 0, // 開啟第幾個
  width: 767, // 尺寸以上tab功能，尺寸以下手風琴功能
  autoClose: true, // 自動關閉其他開啟內容
  openSwitch: true, // 是否可開合/切換
});
```

<!-- tabs:end -->

<style>
  .tabSet{
    margin:4em 0;
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
}

  function tabFunction(obj) {
  // RWD切換判斷，與_variable.scss 的 --RWDWidth連動
  const setRWDWidth = parseInt(window.getComputedStyle(document.documentElement).getPropertyValue('--RWDWidth'));
  const { target, autoClose = true, openContent = false, modeSwitch = false, windowWidth = setRWDWidth, openSwitch = true } = obj;

  const tabSet = document.querySelector(target);
  if (!tabSet) return;

  const tabItems = tabSet.querySelector('.tabItems');
  const tabBtn = tabSet.querySelectorAll('.tabBtn');
  const tabContent = tabSet.querySelectorAll('.tabContent');
  const tabContentIn = tabSet.querySelectorAll('.tabContentIn');
  const defaultIndex = [...tabBtn].indexOf(tabItems.querySelector('.active')) === -1 ? 0 : [...tabBtn].indexOf(tabItems.querySelector('.active'));

  //初始設定
  function _tabInit(targetIndex) {
    tabItems.setAttribute('role', 'tablist');

    tabBtn.forEach((tab, i) => {
      const id = `tab_${_randomLetter(3)}${_randomNumber(3)}`;
      const controls = `${id}_con`;

      tab.setAttribute('role', 'tab');
      tab.setAttribute('id', id);
      tab.setAttribute('aria-controls', controls);
      tab.setAttribute('aria-selected', 'false');
      tab.setAttribute('aria-expanded', 'false');
      tab.setAttribute('tabindex', '-1');
      if (tabContent[i] === undefined) {
        console.error(`tab功能: ${obj.target}內容數量與按鈕數量不符`);
      } else {
        _setAttributeFn(tabContent[i], 'tabpanel', controls, id);
      }

      //模式切換-新增按鈕
      if (modeSwitch) {
        const mobileTabBtn = _createMobileTabBtn(id, controls, tab.textContent);
        tabContent[i].insertAdjacentElement('afterbegin', mobileTabBtn);
      }
    });

    _checkTarget(targetIndex);
    tabSet.dataset.nowIndex = targetIndex;
  }

  // 創建移動版選項按鈕
  function _createMobileTabBtn(id, controls, textContent) {
    const mobileTabBtn = document.createElement('button');
    mobileTabBtn.classList.add('mobileTabBtn');
    mobileTabBtn.setAttribute('id', id);
    mobileTabBtn.setAttribute('aria-controls', controls);
    mobileTabBtn.setAttribute('type', 'button');
    mobileTabBtn.setAttribute('aria-expanded', 'false');
    mobileTabBtn.insertAdjacentHTML('afterbegin', textContent);
    return mobileTabBtn;
  }

  //執行
  _tabInit(defaultIndex);

  //切換動作
  function _checkTarget(targetIndex) {
    tabSet.dataset.nowIndex = targetIndex;

    //點選的按鈕增加active
    tabBtn[targetIndex].classList.add('active');
    tabBtn[targetIndex].setAttribute('aria-selected', 'true');
    tabBtn[targetIndex].setAttribute('aria-expanded', 'true');
    tabBtn[targetIndex].setAttribute('tabindex', '0');

    //移除其他按鈕的active
    const siblingsBtn = [...tabBtn].filter((value) => value !== tabBtn[targetIndex]);
    siblingsBtn.forEach((value) => {
      value.classList.remove('active');
      value.setAttribute('aria-selected', 'false');
      value.setAttribute('aria-expanded', 'false');
      value.setAttribute('tabindex', '-1');
    });

    //內容增加active
    tabContent[targetIndex].removeAttribute('style');

    //移除其他內容的active
    const siblingsPanel = [...tabContent].filter((value) => value !== tabContent[targetIndex]);
    siblingsPanel.forEach((value) => {
      value.style.display = 'none';
    });
  }

  // 是否可開合/切換
  if (openSwitch) {
    // 使用事件委派，將監聽器綁定到 tabSet 上
    tabSet.addEventListener('click', (e) => {
      const target = e.target;
      if (target.classList.contains('tabBtn')) {
        const index = [...tabBtn].indexOf(target);
        _checkTarget(index);
      } else if (modeSwitch && target.classList.contains('mobileTabBtn')) {
        const mobileTabBtn = tabSet.querySelectorAll('.mobileTabBtn');
        const index = [...mobileTabBtn].indexOf(target);
        _mobileTabFn(target, index, mobileTabBtn);
      }
    });

    tabSet.addEventListener('keydown', (e) => {
      if (!e.target.classList.contains('tabBtn')) return;
      let index;
      // 左右操作tab
      if (e.code === 'ArrowRight' || e.code === 'ArrowLeft') {
        const currentIndex = [...tabBtn].indexOf(e.target);
        if (e.code === 'ArrowRight') {
          index = (currentIndex + 1) % tabBtn.length;
        } else {
          index = (currentIndex - 1 + tabBtn.length) % tabBtn.length;
        }
        tabBtn[index].focus();
        _checkTarget(index);
      }
    });
  }

  function _mobileTabFn(btn, i, mobileTabBtn) {
    _jsSlideToggle(tabContentIn[i]);
    tabSet.dataset.nowIndex = i;
    let check = btn.getAttribute('aria-expanded') === 'true' ? false : true;
    btn.setAttribute('aria-expanded', check);
    btn.classList.toggle('active');

    if (!autoClose) return;
    const siblingsMobileTabBtn = [...mobileTabBtn].filter((value) => value !== mobileTabBtn[i]);
    siblingsMobileTabBtn.forEach((value) => {
      value.classList.remove('active');
      value.setAttribute('aria-expanded', 'false');
    });
    const siblingsPanel = [...tabContentIn].filter((value) => value !== tabContentIn[i]);
    siblingsPanel.forEach((value) => {
      _jsSlideUp(value);
    });
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

  function _removeAttributeFn(item) {
    item.removeAttribute('role');
    item.removeAttribute('aria-labelledby');
    item.removeAttribute('id');
  }
  function _setAttributeFn(item, role, id, labelledby) {
    item.setAttribute('role', role);
    item.setAttribute('id', id);
    item.setAttribute('aria-labelledby', labelledby);
  }
  //模式切換-RWD
  function _checkRWD() {
    const tabpanelBtn = tabSet.querySelectorAll('.tabContent .mobileTabBtn');
    const nowOpen = tabSet.dataset.nowIndex;

    // 電腦版
    tabBtn[nowOpen].classList.add('active');
    tabBtn[nowOpen].setAttribute('aria-selected', 'true');
    tabBtn[nowOpen].setAttribute('aria-expanded', 'true');
    tabBtn[nowOpen].setAttribute('tabindex', '0');
    const tabListSiblingsPanelBtn = [...tabBtn].filter((value) => value !== tabBtn[nowOpen]);
    tabListSiblingsPanelBtn.forEach((value) => {
      value.classList.remove('active');
      value.setAttribute('aria-expanded', 'false');
      value.setAttribute('aria-selected', 'false');
      value.setAttribute('tabindex', '-1');
    });

    // 手機版
    tabpanelBtn[nowOpen]?.classList.add('active');
    tabpanelBtn[nowOpen]?.setAttribute('aria-expanded', 'true');
    const tabSiblingsPanelBtn = [...tabpanelBtn].filter((value) => value !== tabpanelBtn[nowOpen]);
    tabSiblingsPanelBtn.forEach((value) => {
      value.classList.remove('active');
      value.setAttribute('aria-expanded', 'false');
    });

    if (window.outerWidth < windowWidth && modeSwitch) {
      //隱藏上方選單
      tabItems.style.display = 'none';

      tabBtn.forEach((tab, i) => {
        const id = tabpanelBtn[i].getAttribute('id');
        const controls = tabpanelBtn[i].getAttribute('aria-controls');

        //顯示所有tab內容標籤
        tabContent[i].removeAttribute('style');
        //移除tab內容標籤
        _removeAttributeFn(tabContent[i]);

        //顯示手風琴標籤按鈕
        tabpanelBtn[i].removeAttribute('style');
        //新增手風琴內容標籤
        _setAttributeFn(tabContentIn[i], 'region', controls, id);
        tabContentIn[i].style.display = 'none';
      });

      if (openContent) {
        tabContentIn.forEach((value, j) => {
          value.style.display = 'block';
          tabpanelBtn[j].classList.add('active');
        });
      } else {
        //隱藏其他手風琴內容
        const siblingsPanel = [...tabContentIn].filter((value) => value !== tabContentIn[nowOpen]);
        siblingsPanel.forEach((value, t) => {
          tabpanelBtn[t].classList.remove('active');
        });
        //展開目前手風琴內容
        tabpanelBtn[nowOpen].classList.add('active');
        tabpanelBtn[nowOpen].setAttribute('aria-expanded', 'true');
        // tabpanelBtn[nowOpen].focus();
        tabContentIn[nowOpen].removeAttribute('style');
      }
    } else if (window.outerWidth >= windowWidth && modeSwitch) {
      //增加上方選單
      tabItems.removeAttribute('style');
      tabItems.setAttribute('role', 'tablist');

      tabBtn.forEach((tab, i) => {
        const id = tabpanelBtn[i].getAttribute('id');
        const controls = tabpanelBtn[i].getAttribute('aria-controls');

        //顯示所有Tab內容
        tabContentIn[i].removeAttribute('style');
        //移除Tab內容標籤
        _removeAttributeFn(tabContentIn[i]);
        tabContentIn[i].removeAttribute('style');

        //隱藏Tab標籤按鈕
        tabpanelBtn[i].style.display = 'none';
        //新增Tab內容標籤
        _setAttributeFn(tabContent[i], 'tabpanel', controls, id);
      });

      //展開目前Tab內容
      tabContent[nowOpen].removeAttribute('style');
      // tabBtn[nowOpen].focus();

      //隱藏其他Tab內容
      const siblingsPanel = [...tabContent].filter((value) => value !== tabContent[nowOpen]);
      siblingsPanel.forEach((value) => {
        value.style.display = 'none';
      });
    }
  }
  _checkRWD();
  window.addEventListener('resize', _checkRWD);
  
}
tabFunction({
  target: '.tabFunction1',
  modeSwitch: true,
});
</script>
