# 無障礙 與 列印

## Accessibility 無障礙

?>相關 css：scss/basic/`_accessibility.scss`

- 設定當物件被`:focus-visible`時的 css 設定  
  除了 input 以外所有 button 和 a 標籤的`:focus-visible`效果
- 導盲磚 css 設定
- nojs css 設定

### 支持無障礙 2.0 AA 等級

?>針對國家通訊傳播委員會頒布之網站無障礙規範 2.0 版，其中許多規範會影響到網站開發者處理無障礙的設定，讓無障礙檢測都能透過鍵盤使用，`HyUI` 在 `scss` 及 `main.js` 已經針對「連結」、「選單操作」...等預先調整了相關的設定，目前是以無障礙 2.0AA 版本為基礎。

!>無障礙以機器檢測與人工檢測為準，HyUI 只能預先處理基礎樣式，如遇到客製專案需求開發，仍需靠開發人員共同處理。

### 快速鍵設定

本網站依 **無障礙網頁設計原則** 建置，網站的主要內容分為 **三大區塊**：

1.  上方功能區塊、 2. 中央內容區塊、 3.下方功能區塊。

- **Alt+U**：上方功能區塊，包括回首頁、網站導覽、網站搜尋、字體選擇、版本選擇等。
- **Alt+C**：中央內容區塊，為本頁主要內容區。
- **Alt+Z**：下方功能區塊。
- **Alt+S**：網站搜尋。

> 如果您的瀏覽器是 `Firefox`，快速鍵的使用方法是 `Shift+Alt+(快速鍵字母)`，例如 `Shift+Alt+C `會跳至網頁中央區塊，以此類推。

![](https://i.imgur.com/bpztC6e.png ':size=300')

?> **當本網站項目頁籤無法以滑鼠點選時，您可利用以下鍵盤操作方式瀏覽資料** <br>
`←` `→` or`↑` `↓`：按**左右鍵**或**上下鍵**移動標籤順序。<br>
`Home` or `End` `→`：可直接**跳至標籤第一項**或者**最後一項**。<br>
`Tab`：停留於該標籤後,可利用 **Tab** 鍵跳至內容瀏覽該筆資料，遇到 **radio** 按鈕時請配合使 `←` `→` or`↑` `↓`鍵移動項目順序。<br>
`Tab + Shift`：按 `Tab + Shift` 可往**回跳至上一筆資料**；當跳回至標籤項目時您可繼續利用`←` `→` or`↑` `↓` 鍵移動標籤順序。

```html
<!-- 直接跳主內容區 -->
<a class="goCenter" href="#center" tabindex="1">按Enter到主內容區</a>
```

### 快捷錨點設定

目前提供之頁面範本，已先置入相對應位置，但可依照專案另外做客製化設定。

```html
<!-- 網站標題區 -->
<a class="accessKeyItem" href="#aU" id="aU" accesskey="U" aria-label="功能區塊">:::</a>
<!-- 網站搜尋 (放置input輸入框) -->
<input name="username" id="mustSameAsId" type="text" placeholder="請輸入文字" accesskey="S" title="請輸入文字" />
<!-- 主要內容區 -->
<a class="accessKeyItem" href="#aC" id="aC" accesskey="C" aria-label="主要內容區">:::</a>
<!-- 頁尾區 -->
<a class="accessKeyItem" href="#aZ" id="aZ" accesskey="Z" aria-label="頁尾區">:::</a>
```

## Print 列印

列印樣式，請於 `print.scss`編寫 SCSS，同樣統一匯出於 `style.css` 內。

?>相關 css：相關 css：scss/basic/`_print.scss`

!>注意媒體格式需使用`@media print`；如需要預覽，請於瀏覽器點選**列印 / 預覽列印** 檢視。
