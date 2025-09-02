# Function Panel / 內容頁控制及顯示模組

?>相關 css：scss/components/`_functionPanel.scss`

> 可自由組合 `發布日期`、`文字大小`、`回上一頁`、`友善列印`、`轉寄友人`、`社群分享`...等目前以提供之模組，在父層包覆 1 個 `functionPanel` 的 div，即可呈現以下樣式。 ，模組無需更改結構只需要放進 `functionPanel` 的 div 即可。

**內含預設模組可參考**

- [fontSize 字型大小](components/fontsize.md)
- [share 社群分享](components/share.md)

**範例**

<div class="functionPanel">
  <div class="fontSizeInner">
    <span>字型大小：</span>
    <ul>
      <li><button type="button" class="smallSize">小</button></li>
      <li><button type="button" class="mediumSize">中</button></li>
      <li><button type="button" class="largeSize">大</button></li>
    </ul>
  </div>
  <a class="functionPanelBtn back" href="javascript:history.back()">回上一頁</a>
  <a class="functionPanelBtn print" href="#">列印</a>
  <a class="functionPanelBtn email" href="#">Email</a>

  <div class="shareBox">
    <button class="functionPanelBtn share">share分享按鈕</button>
    <div class="shareBoxList">
      <ul>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/facebook.svg" alt="facebook" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/x.svg" alt="x" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/threads.svg" alt="Threads" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/line.svg" alt="line" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/youtube.svg" alt="youtube" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/instagram.svg" alt="instagram" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/linkedin.svg" alt="LinkedIn" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/pinterest.svg" alt="Pinterest" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/whatsapp.svg" alt="Whatsapp" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/telegram.svg" alt="Telegram" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/talk.svg" alt="Talk" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/podcast.svg" alt="Podcast" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/discord.svg" alt="Discord" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/plurk.svg" alt="Plurk" /></a>
        </li>
        <li>
          <a href="#"><img src="https://hywebu00.github.io/HyUI_5/images/basic/icon/share/rss.svg" alt="RSS" /></a>
        </li>
      </ul>
    </div>
  </div>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<div class="functionPanel">
  <div class="fontSize">
    <span>字型大小：</span>
    <ul>
      <li><button type="button" class="smallSize">小</button></li>
      <li><button type="button" class="mediumSize">中</button></li>
      <li><button type="button" class="largeSize">大</button></li>
    </ul>
  </div>
  <a class="functionPanelBtn back" href="javascript:history.back()">回上一頁</a>
  <a class="functionPanelBtn print" href="#">列印</a>
  <a class="functionPanelBtn email" href="#">Email</a>
  <div class="shareBox">
    <button class="functionPanelBtn share">share分享按鈕</button>
    <div class="shareBoxList">
      <ul>
        <li>
          <a href="#"><img src="images/basic/icon/share/facebook.svg" alt="facebook" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/x.svg" alt="x" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/threads.svg" alt="Threads" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/line.svg" alt="line" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/youtube.svg" alt="youtube" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/instagram.svg" alt="instagram" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/linkedin.svg" alt="LinkedIn" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/pinterest.svg" alt="Pinterest" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/whatsapp.svg" alt="Whatsapp" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/telegram.svg" alt="Telegram" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/talk.svg" alt="Talk" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/podcast.svg" alt="Podcast" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/discord.svg" alt="Discord" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/plurk.svg" alt="Plurk" /></a>
        </li>
        <li>
          <a href="#"><img src="images/basic/icon/share/rss.svg" alt="RSS" /></a>
        </li>
      </ul>
    </div>
  </div>
</div>
```

#### **JS/JQ**

```javascript
_toggleDropdown('.shareBox .share', '.shareBox .shareBoxList');
```

<!-- tabs:end -->

<style>
  .functionPanel{
    justify-content: flex-start !important;
  }
</style>

<script>
  _toggleDropdown('.shareBox .share', '.shareBox .shareBoxList'); //分享開關切換
</script>
