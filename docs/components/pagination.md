# Paginations 分頁導覽

?>相關 css：scss/components/`_pagination.scss`

<div class="pagination">
  <form action="">
    <div class="formInline">
      共<span>308</span>筆資料，第<span>1/18</span>頁，<label for="petSelect">每頁顯示</label>
      <select name="" id="petSelect" aria-label="每頁顯示">
        <option value="">10</option>
        <option value="">20</option>
        <option value="">30</option>
        <option value="">40</option>
      </select>
      筆<button type="submit" class="btnPrimary btnSubmit">確定</button>
    </div>
  </form>
  <ul class="page">
    <li class="firstArrow"><a href="#" title="第一頁">第一頁</a></li>
    <li class="prevArrow"><a href="#" title="回上一頁">回上一頁</a></li>
    <li class="active"><a href="#">1</a></li>
    <li><a href="#">2</a></li>
    <li><a href="#">3</a></li>
    <li><a href="#">4</a></li>
    <li><a href="#">5</a></li>
    <li class="nextArrow"><a href="#" title="下一頁">下一頁</a></li>
    <li class="lastArrow">
      <a href="#" title="最後一頁">最後一頁</a>
    </li>
  </ul>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<!-- Pagination -->
<div class="pagination">
  <form action="">
    <div class="formInline">
      共<span>308</span>筆資料，第<span>1/18</span>頁，<label for="petSelect">每頁顯示</label>
      <select name="" id="petSelect" aria-label="每頁顯示">
        <option value="">10</option>
        <option value="">20</option>
        <option value="">30</option>
        <option value="">40</option>
      </select>
      筆<button type="submit" class="btnPrimary btnSubmit">確定</button>
    </div>
  </form>
  <ul class="page">
    <li class="firstArrow"><a href="#" title="第一頁">第一頁 </a></li>
    <li class="prevArrow"><a href="#" title="回上一頁">回上一頁 </a></li>
    <li class="active"><a href="#">1</a></li>
    <li><a href="#">2</a></li>
    <li><a href="#">3</a></li>
    <li><a href="#">4</a></li>
    <li><a href="#">5</a></li>
    <li class="nextArrow"><a href="#" title="下一頁">下一頁 </a></li>
    <li class="lastArrow">
      <a href="#" title="最後一頁">最後一頁 </a>
    </li>
  </ul>
</div>
```

<!-- tabs:end -->

<style>
.demo{
    margin:4em 0;
}
.demo .pagination .page li.active a ,.demo .pagination .page li:hover a{
    color: #fff !important;
    background: #06c;
    border: #0059b3 solid 1px;}
@media screen and (max-width: 575px){
    .xs_hidden{
       display:none;
    }
}
 
</style>
