# Table / 表格

?>相關 css：scss/components/`_table.scss`

---

## 基本表格樣式

<table>
 <caption>
  無障礙表格標題
 </caption>
  <thead>
    <tr>
      <th>編號</th>
      <th>姓名</th>
      <th>性別</th>
      <th>年齡</th>
      <th>居住地</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>王大明</td>
      <td>男</td>
      <td>39</td>
      <td>台北市</td>
    </tr>
    <tr>
      <td>2</td>
      <td>李小強</td>
      <td>男</td>
      <td>25</td>
      <td>宜蘭縣</td>
    </tr>
    <tr>
      <td>3</td>
      <td>林珍珍</td>
      <td>女</td>
      <td>33</td>
      <td>新竹市</td>
    </tr>
  </tbody>
</table>

<!-- tabs:start -->

#### **HTML**

```html
<table>
  <caption>
    障礙表格標題
    <!-- 若表格內容複雜，可以補充摘要(summary)來加強說明表格內容，但 內容不要與標題重複 -->
    <!-- <span class="summary">表格摘要</span> -->
  </caption>
  <thead>
    <tr>
      <th>...</th>
      <th>...</th>
      <th>...</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>...</td>
    </tr>
    <tr>
      <td>...</td>
    </tr>
  </tbody>
</table>
```

<!-- tabs:end -->

## 響應式排版表格 - 變動排列方式

支援響應式條列式重新排版表格

使用`before`取代`th`，在`table`上一層使用`<div class="tableList"></div>`將`table`包覆住，即可於手機版重新排版表格樣式。

<!-- panels:start -->
<div class="tableList">
    <table>
        <thead>
            <tr>
                <th>編號</th>
                <th>據點</th>
                <th>地址</th>
                <th>電話</th>
                <th>傳真</th>
                <th>信箱</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>01</td>
                <td>總公司</td>
                <td>新竹縣竹北市台元一街8號5樓之6</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>02</td>
                <td>臺北分公司</td>
                <td>臺北市重慶南路二段51號5樓</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>03</td>
                <td>臺中分公司</td>
                <td>臺中市西屯區臺灣大道三段658號6樓A1</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>04</td>
                <td>高雄分公司</td>
                <td>高雄市新興區中正三路55號26樓之5</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>05</td>
                <td>曼谷分公司</td>
                <td>Room No.2009, 20th F1., Le Concorde Tower, 202 Ratchadapisek Rd., Huaykwang, Bangkok 10310</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>06</td>
                <td>北京</td>
                <td>北京市海淀区安宁庄西路9号院29号楼金泰富地大厦105室</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
        </tbody>
    </table>
</div>
<!-- panels:end -->
<!-- tabs:start -->

#### **HTML**

```html
<div class="tableList">
  <table>
    <caption>
      障礙表格標題
      <!-- 若表格內容複雜，可以補充摘要(summary)來加強說明表格內容，但 內容不要與標題重複 -->
      <!-- <span class="summary">表格摘要</span> -->
    </caption>
    <thead>
      <tr>
        <th>...</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>...</td>
      </tr>
      <tr>
        <td>...</td>
      </tr>
      <tr>
        <td>...</td>
      </tr>
    </tbody>
  </table>
</div>
```

<!-- tabs:end -->

## 響應式排版表格 - 捲軸式

按照專案經驗，在客戶資料上稿常常出現表格會撐出畫面或是破圖的情況，這部分可以使用預設提供之 JavaScript 設定，讓文章內容頁面的表格自動產生響應式橫向捲軸，以防止畫面跑版。

在`table`上一層使用`<div class="tableScroll"></div>`將`table`包覆住，並加上`<button class="scrollTablePrevBtn" type="button">往左捲動</button>`和`<button class="scrollTableNextBtn" type="button">往右捲動</button>`即可。

<!-- panels:start -->
<div class="tableScroll">
  <button class="scrollTablePrevBtn" type="button">往左捲動</button>
  <button class="scrollTableNextBtn" type="button">往右捲動</button>
    <table>
        <thead>
            <tr>
                <th>編號</th>
                <th>據點</th>
                <th>地址</th>
                <th>電話</th>
                <th>傳真</th>
                <th>信箱</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>01</td>
                <td>總公司</td>
                <td>新竹縣竹北市台元一街8號5樓之6</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>02</td>
                <td>臺北分公司</td>
                <td>臺北市重慶南路二段51號5樓</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>03</td>
                <td>臺中分公司</td>
                <td>臺中市西屯區臺灣大道三段658號6樓A1</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>04</td>
                <td>高雄分公司</td>
                <td>高雄市新興區中正三路55號26樓之5</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>05</td>
                <td>曼谷分公司</td>
                <td>Room No.2009, 20th F1., Le Concorde Tower, 202 Ratchadapisek Rd., Huaykwang, Bangkok 10310</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
            <tr>
                <td>06</td>
                <td>北京</td>
                <td>北京市海淀区安宁庄西路9号院29号楼金泰富地大厦105室</td>
                <td>02-12345678</td>
                <td>02-12345678</td>
                <td><a href="#"><img src="https://hywebu00.github.io/hyui_flex/images/icon/icon_mail.svg" alt=""></a></td>
            </tr>
        </tbody>
    </table>
</div>
<!-- panels:end -->
<!-- tabs:start -->

#### **HTML**

```html
<div class="tableScroll">
  <button class="scrollTablePrevBtn" type="button">往左捲動</button>
  <button class="scrollTableNextBtn" type="button">往右捲動</button>
  <table>
    <caption>
      障礙表格標題
      <!-- 若表格內容複雜，可以補充摘要(summary)來加強說明表格內容，但 內容不要與標題重複 -->
      <!-- <span class="summary">表格摘要</span> -->
    </caption>
    <thead>
      <tr>
        <th>...</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>...</td>
      </tr>
      <tr>
        <td>...</td>
      </tr>
      <tr>
        <td>...</td>
      </tr>
    </tbody>
  </table>
</div>
```

<!-- tabs:end -->

<style>
/* 取消 markdown 預設狀態 */
.markdown-section p.tip, .markdown-section tr:nth-child(2n) {
    background-color:unset;
}
.markdown-section table{
  display:table;
}
table img{
  width:20px;
}
td:has(img){
  text-align:center;
}
</style>
<script>
function scrollTables() {
  const el = document.querySelectorAll('.tableScroll');
  if (el.length === 0) return;

  el.forEach((elem) => {
    const table = elem.querySelector('table');
    const caption = elem.querySelector('caption');
    const prevBtn = elem.querySelector('.scrollTablePrevBtn');
    const nextBtn = elem.querySelector('.scrollTableNextBtn');
    if (!prevBtn || !nextBtn) {
      console.error('表格捲動功能: prevBtn 或 nextBtn 無法抓到，請檢查Html結構');
      return;
    }

    if (caption) {
      let captionMargin = parseInt(window.getComputedStyle(caption).marginBottom.replace('px', '')) || 0;

      prevBtn.style.top = `${caption.offsetHeight + captionMargin}px`;
      nextBtn.style.top = `${caption.offsetHeight + captionMargin}px`;
    }
    const tableScrollIn = document.createElement('div');
    tableScrollIn.className = 'tableScrollIn';
    tableScrollIn.insertAdjacentElement('afterbegin', table);
    elem.insertAdjacentElement('beforeend', tableScrollIn);

    let tableScrollLeft = tableScrollIn.scrollLeft;
    let tableClientWidth = tableScrollIn.clientWidth;
    let tableScrollWidth = tableScrollIn.scrollWidth;

    tableScrollIn.addEventListener('scroll', () => {
      _checkScroll(tableScrollLeft, tableClientWidth, tableScrollWidth);
    });

    function _checkScroll(tableScrollLeft, tableClientWidth, tableScrollWidth) {
      tableScrollLeft = tableScrollIn.scrollLeft;
      tableClientWidth = tableScrollIn.clientWidth;
      tableScrollWidth = table.scrollWidth;

      if (tableScrollLeft >= 0 && tableScrollLeft + tableClientWidth < tableScrollWidth) {
        nextBtn.style.display = 'block';
      } else {
        nextBtn.style.display = 'none';
      }
      if (tableScrollLeft > 0) {
        prevBtn.style.display = 'block';
      } else {
        prevBtn.style.display = 'none';
      }
    }

    _checkScroll(tableScrollLeft, tableClientWidth, tableScrollWidth);
    window.addEventListener('resize', () => _checkScroll(tableScrollLeft, tableClientWidth, tableScrollWidth));

    prevBtn.addEventListener('click', (e) => {
      e.preventDefault();
      tableScrollIn.scrollBy({ left: -100, behavior: 'smooth' });
    });
    nextBtn.addEventListener('click', (e) => {
      e.preventDefault();
      tableScrollIn.scrollBy({ left: 100, behavior: 'smooth' });
    });
  });
}
window.addEventListener('load', () => scrollTables());
</script>
<link rel="stylesheet" href="https://hywebu00.github.io/HyUI_5/css/style.css" />
