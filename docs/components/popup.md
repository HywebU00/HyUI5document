# Popup 彈出視窗/燈箱

?>相關 css：scss/components/`_popup_.scss`

使用`fancybox`模組，請確認是否有購買相關使用證明。

## Html

不同的燈箱對應按鈕不同`id`，可自行變更。

按鈕需增加

- `data-fancybox`啟動燈箱功能
- `data-src`對應燈箱內容的`id`，可自行變更

!>因為是對應 id，故`data-src`需要加`#`。

燈箱內容需增加

- `id`對應按鈕的`data-src`。

預設提供兩種 popup 大小用的`class`

- 彈出對話框(大)：`.popupB`
- 彈出對話框(小)：`.popupS`

`class` 需與`id`設在同一個 div 上。  
若需要一進入就開燈箱時，在燈箱內容上增加`.showPopup`即可。

!>一進入就開燈箱就算沒有按鈕，還是需要輸入 id。

<!-- tabs:start -->

#### **HTML**

```html
<div id="popup" class="popupB showPopup"></div>
```

<!-- tabs:end -->

**範例**

<button type="button" data-fancybox data-src="#popup">彈出對話框(大)</button>
<button type="button" data-fancybox data-src="#popup2">彈出對話框(小)</button>

<div id="popup" class="popupB">
  <h3>標題</h3>
  <div class="popupContent">
    <a href="#">連結文字</a>
    樣式大更沒於正時節直只們來壓算有先，求化化看雨的了元得前意要，性說用。以是一分，首字地旅紀親朋經有，在沒許、兒讓靈身不；候案司通資鄉下一支情西也哥際發你也是濟言通海後的健童頭各便。大更沒於正時節直只們來壓算有先，求化化看雨的了元得前意要，性說用。以是一分，首字地旅紀親朋經有，在沒許、兒讓靈身不；候案司通資鄉下一支情西也哥際發你也是濟言通海後的健童頭各便。
  </div>
  <div class="btnBox">
    <button class="cancel btnSecondary" type="button">取消</button>
    <button class="submit btnPrimary" type="submit">確認</button>
  </div>
</div>

<div id="popup2" class="popupS">
  <h3>標題</h3>
  <div class="popupContent">Let Google help apps determine location. This means sending anonymous location data to Google, even when no apps are running.</div>
  <div class="btnBox">
    <button class="cancel btnSecondary" type="button">取消</button>
    <button class="submit btnPrimary" type="submit">確認</button>
  </div>
</div>

<!-- tabs:start -->

#### **彈出對話框(大) HTML**

```html
<button type="button" data-fancybox data-src="#popup">彈出對話框(大)</button>

<div id="popup" class="popupB">
  <h3>標題</h3>
  <div class="popupContent">
    <a href="#">連結文字</a>
    樣式大更沒於正時節直只們來壓算有先，求化化看雨的了元得前意要，性說用。以是一分，首字地旅紀親朋經有，在沒許、兒讓靈身不；候案司通資鄉下一支情西也哥際發你也是濟言通海後的健童頭各便。大更沒於正時節直只們來壓算有先，求化化看雨的了元得前意要，性說用。以是一分，首字地旅紀親朋經有，在沒許、兒讓靈身不；候案司通資鄉下一支情西也哥際發你也是濟言通海後的健童頭各便。
  </div>
  <div class="btnBox">
    <button class="cancel btnSecondary" type="button">取消</button>
    <button class="submit btnPrimary" type="submit">確認</button>
  </div>
</div>
```

#### **彈出對話框(小) HTML**

```html
<button type="button" data-fancybox data-src="#popup2">彈出對話框(小)</button>

<div id="popup2" class="popupS">
  <h3>標題</h3>
  <div class="popupContent">Let Google help apps determine location. This means sending anonymous location data to Google, even when no apps are running.</div>
  <div class="btnBox">
    <button class="cancel btnSecondary" type="button">取消</button>
    <button class="submit btnPrimary" type="submit">確認</button>
  </div>
</div>
```

<!-- tabs:end -->

## 圖片

圖片分為單張或相簿

### 單張

只出現一張，每張圖片各別設定。

- `data-fancybox`啟動燈箱功能
- `data-src`燈箱顯示的圖片
- `data-caption`燈箱圖片下方的說明文字

**範例**

<a
data-fancybox
data-src="https://images.unsplash.com/photo-1748257615880-6243d0d7422f?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1748257615880-6243d0d7422f?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="圖片說明" />
</a>

  <!-- tabs:start -->

#### **HTML**

```html
<a data-fancybox data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>
```

<!-- tabs:end -->

### 相簿

可左右切換不同照片，不同的相簿只需要更換`data-fancybox="gallery"`即可。  
相簿有兩種做法

1. 照片全部於列表中顯示，點選後開燈箱並可以左右切換。

**範例**

<a
data-fancybox="gallery"
data-src="https://images.unsplash.com/photo-1748257615880-6243d0d7422f?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1748257615880-6243d0d7422f?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="" />
</a>
<a
data-fancybox="gallery"
data-src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="" />
</a>
<a
data-fancybox="gallery"
data-src="https://images.unsplash.com/photo-1534361960057-19889db9621e?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1534361960057-19889db9621e?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="" />
</a>

  <!-- tabs:start -->

#### **HTML**

```html
<a data-fancybox="gallery" data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>
<a data-fancybox="gallery" data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>
<a data-fancybox="gallery" data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>
```

<!-- tabs:end -->

2. 列表中每一張圖都是一本相簿，點開後可以左右切換該本相簿中的圖片。

!>列表圖本身就算一張圖片。

**範例**

<a
data-fancybox="gallery1"
data-src="https://images.unsplash.com/photo-1748257615880-6243d0d7422f?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1748257615880-6243d0d7422f?q=80&w=1493&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="圖片說明" />
</a>
<a
data-fancybox="gallery2"
data-src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="圖片說明" />
</a>
<a
data-fancybox="gallery3"
data-src="https://images.unsplash.com/photo-1534361960057-19889db9621e?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
<img src="https://images.unsplash.com/photo-1534361960057-19889db9621e?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" width="200" height="150" alt="圖片說明" />
</a>

<div class="picBox">
<a
data-fancybox="gallery1"
data-src="https://images.unsplash.com/photo-1746730406177-f8562813b938?q=80&w=1472&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
</a>
<a
data-fancybox="gallery1"
data-src="https://images.unsplash.com/photo-1750126833705-ba98013f16f3?q=80&w=1171&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
</a>
<a
data-fancybox="gallery2"
data-src="https://images.unsplash.com/photo-1489824904134-891ab64532f1?q=80&w=1631&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
</a>
<a
data-fancybox="gallery2"
data-src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
</a>
<a
data-fancybox="gallery3"
data-src="https://images.unsplash.com/photo-1517423440428-a5a00ad493e8?q=80&w=1949&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
</a>
<a
data-fancybox="gallery3"
data-src="https://images.unsplash.com/photo-1518717758536-85ae29035b6d?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
data-caption="圖片說明">
</a>
</div>

  <!-- tabs:start -->

#### **HTML**

```html
<a data-fancybox="gallery1" data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>
<a data-fancybox="gallery2" data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>
<a data-fancybox="gallery3" data-src="..." data-caption="圖片說明"><img src="..." alt="圖片說明" /></a>

<div style="display:none">
  <a data-fancybox="gallery1" data-src="..." data-caption="圖片說明"></a>
  <a data-fancybox="gallery1" data-src="..." data-caption="圖片說明"></a>
  <a data-fancybox="gallery2" data-src="..." data-caption="圖片說明"></a>
  <a data-fancybox="gallery2" data-src="..." data-caption="圖片說明"></a>
  <a data-fancybox="gallery3" data-src="..." data-caption="圖片說明"></a>
  <a data-fancybox="gallery3" data-src="..." data-caption="圖片說明"></a>
</div>
```

<!-- tabs:end -->
<style>
  [data-src="#popup"]{
    margin-bottom:10px;
  }
  .picBox{
    display:none !important;
  }
</style>
