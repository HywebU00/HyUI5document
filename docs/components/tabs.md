# Tabs / 頁籤

?>相關 css：scss/components/`tabs.scss`

提供一組**可響應式及通過無障礙** tab 遊走之 tab 頁籤模組。

- 頁籤沒有數量限制，但請注意畫面上的均衡比例。建議勿超過 5 組為宜。
- 可客製不同樣式，於`tabs`後方新增不同的 `classnName`即可。>
- 可自訂響應式斷點(Breakpoints)，如有 特殊需求，可另外替換變數或數值。

<div class="tabSet">
                <div class="tabItems">
                  <button type="button" class="item">頁籤A</button>
                  <button type="button" class="item">頁籤B</button>
                  <button type="button" class="item">頁籤C</button>
                  <button type="button" class="item">頁籤D</button>
                </div>
                <div class="tabContentGroup">
                  <div class="tabContent" title="頁籤A內容">
                    <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
                    <p><a href="#">頁籤項目一的內容1-1</a></p>
                    <p><a href="#">頁籤項目一的內容1-2</a></p>
                    <p><a href="#">頁籤項目一的內容1-3</a></p>
                  </div>
                  <div class="tabContent" title="頁籤B內容">
                    <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
                    <p><a href="#">頁籤項目二的內容2-1</a></p>
                    <p><a href="#">頁籤項目二的內容2-2</a></p>
                    <p><a href="#">頁籤項目二的內容2-3</a></p>
                    <div><a href="#">more</a></div>
                  </div>
                  <div class="tabContent" title="頁籤C內容">
                    <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
                    <p>＊＊＊這個頁籤內容沒有 a 或其他 focusable 元件</p>
                  </div>
                  <div class="tabContent" title="頁籤D內容">
                    <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
                    <p><a href="#">頁籤項目四的內容4-1</a></p>
                    <p><a href="#">頁籤項目四的內容4-2</a></p>
                  </div>
                </div>
              </div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="tabSet">
  <div class="tabItems">
    <button type="button" class="item">頁籤A</button>
    <button type="button" class="item">頁籤B</button>
    <button type="button" class="item">頁籤C</button>
    <button type="button" class="item">頁籤D</button>
  </div>
  <div class="tabContentGroup">
    <div class="tabContent" title="頁籤A內容">
      <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
      <p><a href="#">頁籤項目一的內容1-1</a></p>
      <p><a href="#">頁籤項目一的內容1-2</a></p>
      <p><a href="#">頁籤項目一的內容1-3</a></p>
    </div>
    <div class="tabContent" title="頁籤B內容">
      <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
      <p><a href="#">頁籤項目二的內容2-1</a></p>
      <p><a href="#">頁籤項目二的內容2-2</a></p>
      <p><a href="#">頁籤項目二的內容2-3</a></p>
      <div><a href="#">more</a></div>
    </div>
    <div class="tabContent" title="頁籤C內容">
      <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
      <p>＊＊＊這個頁籤內容沒有 a 或其他 focusable 元件</p>
    </div>
    <div class="tabContent" title="頁籤D內容">
      <div>頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容頁籤內容</div>
      <p><a href="#">頁籤項目四的內容4-1</a></p>
      <p><a href="#">頁籤項目四的內容4-2</a></p>
    </div>
  </div>
</div>
```

#### **JS**

```javascript
function tabFunction(elem) {
  const activeClass = 'active'; // --- 啟動的 class
  const tabSet = document.querySelectorAll(elem); // --- tab名稱
  tabSet.forEach((a) => {
    const tabBtn = a.querySelectorAll('.tabItems button'); // --- 頁籤按鈕
    const tabBtnLength = tabBtn.length; // --- 頁籤按鈕數量
    const tabContent = a.querySelectorAll('.tabContentGroup .tabContent'); // --- 頁籤內容
    tabBtn[0].classList.add('active');
    tabContent[0].classList.add('active');
    tabBtn.forEach((v, i) => {
      const thisBtn = tabBtn[i]; // --- 綁定這一個頁籤按鈕
      const thisContent = tabContent[i]; // --- 綁定這一個頁籤內容
      const thisPrevItem = tabContent[i - 1]; // --- 綁定前一個頁籤按鈕
      const itemAllA = thisContent.querySelectorAll('[href], input'); // --- 這一個頁籤內容所有a和input項目
      let prevItemAllA;
      if (thisPrevItem !== undefined) {
        prevItemAllA = thisPrevItem.querySelectorAll('[href], input'); // --- 前一個頁籤內容所有a和input項目
      }
      const isFirstTab = i === 0; // --- 如果是第一個頁籤
      const isLastTab = i === tabBtnLength - 1; // --- 如果是最後一個頁籤
      const itemFirstA = itemAllA[0]; // --- 頁籤內容第一個a或是input
      const itemLastA = itemAllA[itemAllA.length - 1]; // --- 頁籤內容最後一個a或是input
      let prevItemLastA;
      if (thisPrevItem !== undefined) {
        prevItemLastA = prevItemAllA[prevItemAllA.length - 1]; // --- 前一個頁籤的最後一個a或是input
      }
      // --- thisBtn頁籤觸發focus內容裡的第一個a
      thisBtn.addEventListener('keydown', (e) => {
        // --- 頁籤第幾個按鈕觸發時
        if (e.which === 9 && !e.shiftKey) {
          // --- e.which偵測按下哪個案件，9代表tab，shiftKey代表shift
          e.preventDefault();
          startTab(i, tabBtn, tabContent); // --- 啟動頁籤切換功能
          if (itemAllA.length) {
            // --- type number = true，0是false
            itemFirstA.focus(); // --- 第一個a或是input focus
          } else {
            tabBtn[i + 1].focus(); // --- 當內容沒有a或是input跳轉下一個tab
          }
        } else if (e.which === 9 && e.shiftKey && !isFirstTab) {
          e.preventDefault();
          startTab(i - 1, tabBtn, tabContent); // --- 啟動頁籤切換功能
          if (prevItemAllA.length) {
            prevItemLastA.focus(); // --- 前一個頁籤內容的最後一個a或是input focus
          } else {
            tabBtn[i - 1].focus(); // --- 當內容沒有a或是input跳轉上一個tab
          }
        }
      });
      // --- 當按下shift+tab且為該內容的第一個a或是input
      // --- 將focus目標轉回tab頁籤上，呼叫上方功能startTab(i - 1);往前一個頁籤
      if (itemFirstA !== undefined) {
        itemFirstA.addEventListener('keydown', (e) => {
          if (e.which === 9 && e.shiftKey) {
            e.preventDefault();
            tabBtn[i].focus();
          }
        });
      }
      // --- 當按下tab且為該內容的最後一個a或是input
      // --- focus到下一個頁籤
      if (itemLastA !== undefined) {
        itemLastA.addEventListener('keydown', (e) => {
          if (e.which === 9 && !e.shiftKey && !isLastTab) {
            e.preventDefault();
            tabBtn[i + 1].focus();
          }
        });
      }
      // --- 滑鼠點擊事件
      tabBtn[i].addEventListener(
        'click',
        (e) => {
          startTab(i, tabBtn, tabContent);
        },
        false
      );
    });
  });
  function startTab(now, tabBtn, tabContent) {
    if (tabBtn !== undefined) {
      tabBtn.forEach((i) => {
        i.classList.remove(activeClass);
      });
      tabBtn[now].classList.add(activeClass);
      // --- 頁籤按鈕增加指定class(active)，其他頁籤移除指定class
      tabContent.forEach((i) => {
        i.classList.remove(activeClass);
      });
      tabContent[now].classList.add(activeClass);
      // --- 顯示當下頁籤內，隱藏其他內容
    }
  }
}
tabFunction('.tabSet'); // tab功能
```

<!-- tabs:end -->

<style>
  .tabSet{
    margin:4em 0;
  }
</style>
<script>
  function tabFunction(elem) {
  const activeClass = 'active'; // --- 啟動的 class
  const tabSet = document.querySelectorAll(elem); // --- tab名稱
  tabSet.forEach((a) => {
    const tabBtn = a.querySelectorAll('.tabItems button'); // --- 頁籤按鈕
    const tabBtnLength = tabBtn.length; // --- 頁籤按鈕數量
    const tabContent = a.querySelectorAll('.tabContentGroup .tabContent'); // --- 頁籤內容
    tabBtn[0].classList.add('active');
    tabContent[0].classList.add('active');
    tabBtn.forEach((v, i) => {
      const thisBtn = tabBtn[i]; // --- 綁定這一個頁籤按鈕
      const thisContent = tabContent[i]; // --- 綁定這一個頁籤內容
      const thisPrevItem = tabContent[i - 1]; // --- 綁定前一個頁籤按鈕
      const itemAllA = thisContent.querySelectorAll('[href], input'); // --- 這一個頁籤內容所有a和input項目
      let prevItemAllA;
      if (thisPrevItem !== undefined) {
        prevItemAllA = thisPrevItem.querySelectorAll('[href], input'); // --- 前一個頁籤內容所有a和input項目
      }
      const isFirstTab = i === 0; // --- 如果是第一個頁籤
      const isLastTab = i === tabBtnLength - 1; // --- 如果是最後一個頁籤
      const itemFirstA = itemAllA[0]; // --- 頁籤內容第一個a或是input
      const itemLastA = itemAllA[itemAllA.length - 1]; // --- 頁籤內容最後一個a或是input
      let prevItemLastA;
      if (thisPrevItem !== undefined) {
        prevItemLastA = prevItemAllA[prevItemAllA.length - 1]; // --- 前一個頁籤的最後一個a或是input
      }
      // --- thisBtn頁籤觸發focus內容裡的第一個a
      thisBtn.addEventListener('keydown', (e) => {
        // --- 頁籤第幾個按鈕觸發時
        if (e.which === 9 && !e.shiftKey) {
          // --- e.which偵測按下哪個案件，9代表tab，shiftKey代表shift
          e.preventDefault();
          startTab(i, tabBtn, tabContent); // --- 啟動頁籤切換功能
          if (itemAllA.length) {
            // --- type number = true，0是false
            itemFirstA.focus(); // --- 第一個a或是input focus
          } else {
            tabBtn[i + 1].focus(); // --- 當內容沒有a或是input跳轉下一個tab
          }
        } else if (e.which === 9 && e.shiftKey && !isFirstTab) {
          e.preventDefault();
          startTab(i - 1, tabBtn, tabContent); // --- 啟動頁籤切換功能
          if (prevItemAllA.length) {
            prevItemLastA.focus(); // --- 前一個頁籤內容的最後一個a或是input focus
          } else {
            tabBtn[i - 1].focus(); // --- 當內容沒有a或是input跳轉上一個tab
          }
        }
      });
      // --- 當按下shift+tab且為該內容的第一個a或是input
      // --- 將focus目標轉回tab頁籤上，呼叫上方功能startTab(i - 1);往前一個頁籤
      if (itemFirstA !== undefined) {
        itemFirstA.addEventListener('keydown', (e) => {
          if (e.which === 9 && e.shiftKey) {
            e.preventDefault();
            tabBtn[i].focus();
          }
        });
      }
      // --- 當按下tab且為該內容的最後一個a或是input
      // --- focus到下一個頁籤
      if (itemLastA !== undefined) {
        itemLastA.addEventListener('keydown', (e) => {
          if (e.which === 9 && !e.shiftKey && !isLastTab) {
            e.preventDefault();
            tabBtn[i + 1].focus();
          }
        });
      }
      // --- 滑鼠點擊事件
      tabBtn[i].addEventListener(
        'click',
        (e) => {
          startTab(i, tabBtn, tabContent);
        },
        false
      );
    });
  });
  function startTab(now, tabBtn, tabContent) {
    if (tabBtn !== undefined) {
      tabBtn.forEach((i) => {
        i.classList.remove(activeClass);
      });
      tabBtn[now].classList.add(activeClass);
      // --- 頁籤按鈕增加指定class(active)，其他頁籤移除指定class
      tabContent.forEach((i) => {
        i.classList.remove(activeClass);
      });
      tabContent[now].classList.add(activeClass);
      // --- 顯示當下頁籤內，隱藏其他內容
    }
}
}
tabFunction('.tabSet'); // tab功能
</script>
