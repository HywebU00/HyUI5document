# formNotice / 提示訊息

?>相關 css：scss/components/`_form_.scss`
在無障礙的需求中，若是有在填寫表單會出發相關訊息的時候，再通知區塊時需要常駐一個元件並設定`role="alert"`，後續觸發的訊息都需要加入到該元件中。
通常用於表單輸入狀態之提示，可自由替換提示訊息之文本。

<section class="demo">
<div role="alert" id="alert">
  <div class="formNotice">
    <span>這是一般提醒訊息區塊</span>
  </div>
  <div class="formNoticeInfo">
    <span>這是一般提醒訊息區塊</span>
  </div>
  <div class="formNoticeWarning">
    <span>這似乎不是一個正常的Email格式</span>
  </div>
  <div class="formNoticeError">
    <span>您輸入的帳號密碼有誤！</span>
  </div>
</div>
</section>

## 預設提示訊息

<!-- tabs:start -->

#### **HTML**

```html
<div role="alert" id="alert">
  <div class="formNotice">
    <span>這是一般提醒訊息區塊</span>
  </div>
  <div class="formNoticeInfo">
    <span>這是一般提醒訊息區塊</span>
  </div>
  <div class="formNoticeWarning">
    <span>這似乎不是一個正常的Email格式</span>
  </div>
  <div class="formNoticeError">
    <span>您輸入的帳號密碼有誤！</span>
  </div>
</div>
```

<!-- tabs:end -->

<style>
  .demo{
    margin:4em 0;
  }
</style>
