# fatFooter 頁尾選單

?>相關 css：scss/components/`_fatFooter.scss`

**範例**

<div class="fatFooter">
  <div class="container">
    <button type="button" aria-expanded="true" id="fatFooterBtn" aria-label="開關頁尾網站導覽"></button>
    <nav aria-label="頁尾網站導覽">
      <ul>
        <li>
          <a href="#">關於本局</a>
          <ul>
            <li><a href="#">本局沿革</a></li>
            <li><a href="#">本局願景</a></li>
            <li><a href="#">組織介紹</a></li>
            <li><a href="#">本局願景</a></li>
            <li><a href="#">局處執掌</a></li>
            <li><a href="#">重大政策</a></li>
            <li><a href="#">施政重點</a></li>
            <li><a href="#">本局位置</a></li>
          </ul>
        </li>
        <li>
          <a href="#">訊息公告</a>
          <ul>
            <li><a href="#">本局公告</a></li>
            <li><a href="#">環保署公告</a></li>
            <li><a href="#">環境用藥公告</a></li>
            <li><a href="#">環保專案成果報告</a></li>
          </ul>
        </li>
        <li>
          <a href="#">業務專區</a>
          <ul>
            <li><a href="#">化學物質</a></li>
            <li><a href="#">毒性化學物質</a></li>
            <li><a href="#">危害性化學物質災害防救</a></li>
            <li><a href="#">環境用藥</a></li>
            <li><a href="#">石綿危害資訊</a></li>
          </ul>
        </li>
        <li>
          <a href="#">便民服務</a>
          <ul>
            <li><a href="#">線上服務</a></li>
            <li><a href="#">教育宣導</a></li>
            <li><a href="#">影音專區</a></li>
            <li><a href="#">下載專區</a></li>
            <li><a href="#">常見問答</a></li>
            <li><a href="#">相關連結</a></li>
            <li><a href="#">訂閱電子報</a></li>
          </ul>
        </li>
        <li>
          <a href="#">政府資訊公開</a>
          <ul>
            <li><a href="#">行政院環境保護署資訊公開要點</a></li>
            <li><a href="#">預算及會計月報</a></li>
            <li><a href="#">性別平等專區</a></li>
            <li><a href="#">人權專區</a></li>
            <li><a href="#">環境統計資料庫</a></li>
            <li><a href="#">業務標準作業流程</a></li>
            <li><a href="#">行政院環保署Open Data資料集</a></li>
          </ul>
        </li>
        <li>
          <a href="#">法規專區</a>
          <ul>
            <li><a href="#">主管法規查詢系統</a></li>
            <li><a href="#">全國法規資料庫</a></li>
          </ul>
        </li>
      </ul>
    </nav>
  </div>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="fatFooter">
  <div class="container">
    <button type="button" aria-expanded="true" id="fatFooterBtn" aria-label="開關頁尾網站導覽"></button>
    <nav aria-label="頁尾網站導覽">
      <ul>
        <li>
          <a href="#">關於本局</a>
          <ul>
            <li><a href="#">本局沿革</a></li>
            <li><a href="#">本局願景</a></li>
            <li><a href="#">組織介紹</a></li>
            <li><a href="#">本局願景</a></li>
            <li><a href="#">局處執掌</a></li>
            <li><a href="#">重大政策</a></li>
            <li><a href="#">施政重點</a></li>
            <li><a href="#">本局位置</a></li>
          </ul>
        </li>
        <li>
          <a href="#">訊息公告</a>
          <ul>
            <li><a href="#">本局公告</a></li>
            <li><a href="#">環保署公告</a></li>
            <li><a href="#">環境用藥公告</a></li>
            <li><a href="#">環保專案成果報告</a></li>
          </ul>
        </li>
        <li>
          <a href="#">業務專區</a>
          <ul>
            <li><a href="#">化學物質</a></li>
            <li><a href="#">毒性化學物質</a></li>
            <li><a href="#">危害性化學物質災害防救</a></li>
            <li><a href="#">環境用藥</a></li>
            <li><a href="#">石綿危害資訊</a></li>
          </ul>
        </li>
        <li>
          <a href="#">便民服務</a>
          <ul>
            <li><a href="#">線上服務</a></li>
            <li><a href="#">教育宣導</a></li>
            <li><a href="#">影音專區</a></li>
            <li><a href="#">下載專區</a></li>
            <li><a href="#">常見問答</a></li>
            <li><a href="#">相關連結</a></li>
            <li><a href="#">訂閱電子報</a></li>
          </ul>
        </li>
        <li>
          <a href="#">政府資訊公開</a>
          <ul>
            <li><a href="#">行政院環境保護署資訊公開要點</a></li>
            <li><a href="#">預算及會計月報</a></li>
            <li><a href="#">性別平等專區</a></li>
            <li><a href="#">人權專區</a></li>
            <li><a href="#">環境統計資料庫</a></li>
            <li><a href="#">業務標準作業流程</a></li>
            <li><a href="#">行政院環保署Open Data資料集</a></li>
          </ul>
        </li>
        <li>
          <a href="#">法規專區</a>
          <ul>
            <li><a href="#">主管法規查詢系統</a></li>
            <li><a href="#">全國法規資料庫</a></li>
          </ul>
        </li>
      </ul>
    </nav>
  </div>
</div>
```

<!-- tabs:end -->

<style>
  .fatFooter nav{
    width:100%;
  }
  .fatFooter nav > ul{
    width:100%;
  }
</style>
<script>
  function fatFooter() {
  const fatFooterBtn = document.querySelector('#fatFooterBtn');

  if (!fatFooterBtn) return;

  const fatFooterCon = document.querySelectorAll('.fatFooter nav > ul > li > ul');

  let idArray = [];
  fatFooterCon.forEach((item, i) => {
    idArray.push(`fatFooter${i}`);
    item.setAttribute('id', `fatFooter${i}_con`);
    item.setAttribute('aria-labelledby', `fatFooterBtn`);
  });

  fatFooterBtn.setAttribute('aria-controls', idArray.join(' '));
  fatFooterBtn.setAttribute('aria-expanded', 'true');

  fatFooterBtn.addEventListener('click', (e) => {
    e.preventDefault();
    fatFooterCon.forEach((i) => _toggleFatFooter(i, 400));
  });

  function _toggleFatFooter(element, time = 200) {
    let ele = window.getComputedStyle(element);

    let display = ele.display;
    let speed = time;
    element.style.display = display;
    if (display === 'none') {
      element.style.display = 'flex';
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
      fatFooterBtn.setAttribute('aria-expanded', 'true');
      fatFooterBtn.classList.remove('active');
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
      fatFooterBtn.setAttribute('aria-expanded', 'false');
      fatFooterBtn.classList.add('active');
    }
  }
}
window.addEventListener('load', () => fatFooter());
</script>
