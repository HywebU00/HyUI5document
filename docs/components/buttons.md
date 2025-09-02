# Button 按鈕

?>相關 css：scss/components/ `_button.scss`

- 按鈕狀態：default、disabled
- 按鈕樣式：主要、次要、一般
- 按鈕可添加 icon
- 按鈕可添加大小

**範例**

<div class="bp">
  <div class="btnGrp">
    <div class="title">主要按鈕<br />(Primary)</div>
    <ul>
      <li>
        <div class="title">Small</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnPrimary btnS"><i class="i_language_w"></i>Small button　+</button>
              <button class="btnPrimary btnS bd"><i class="i_language_b"></i>Small button　+</button>
              <button class="btnPrimary btnS nbd"><i class="i_language_b"></i>Small button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Normal</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnPrimary"><i class="i_language_w"></i>Normal button　+</button>
              <button class="btnPrimary bd"><i class="i_language_b"></i>Normal button　+</button>
              <button class="btnPrimary nbd"><i class="i_language_b"></i>Normal button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Large</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnPrimary btnL"><i class="i_language_w"></i>Large button　+</button>
              <button class="btnPrimary btnL bd"><i class="i_language_b"></i>Large button　+</button>
              <button class="btnPrimary btnL nbd"><i class="i_language_b"></i>Large button　+</button>
            </div>
          </li>
        </ul>
      </li>
    </ul>

  </div>
  <div class="btnGrp">
    <div class="title">次要按鈕<br />(Secondary)</div>
    <ul>
      <li>
        <div class="title">Small</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnSecondary btnS"><i class="i_language_w"></i>Small button　+</button>
              <button class="btnSecondary btnS bd"><i class="i_language_b"></i>Small button　+</button>
              <button class="btnSecondary btnS nbd"><i class="i_language_b"></i>Small button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Normal</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnSecondary"><i class="i_language_w"></i>Normal button　+</button>
              <button class="btnSecondary bd"><i class="i_language_b"></i>Normal button　+</button>
              <button class="btnSecondary nbd"><i class="i_language_b"></i>Normal button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Large</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnSecondary btnL"><i class="i_language_w"></i>Large button　+</button>
              <button class="btnSecondary btnL bd"><i class="i_language_b"></i>Large button　+</button>
              <button class="btnSecondary btnL nbd"><i class="i_language_b"></i>Large button　+</button>
            </div>
          </li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="btnGrp">
    <div class="title">一般/默認按鈕<br />(Normal)</div>
    <ul>
      <li>
        <div class="title">Small</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnNormal btnS"><i class="i_language_dk"></i>Small button　+</button>
              <button class="btnNormal btnS bd"><i class="i_language_dk"></i>Small button　+</button>
              <button class="btnNormal btnS nbd"><i class="i_language_dk"></i>Small button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Normal</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnNormal"><i class="i_language_dk"></i>Normal button　+</button>
              <button class="btnNormal bd"><i class="i_language_dk"></i>Normal button　+</button>
              <button class="btnNormal nbd"><i class="i_language_dk"></i>Normal button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Large</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnNormal btnL"><i class="i_language_dk"></i>Large button　+</button>
              <button class="btnNormal btnL bd"><i class="i_language_dk"></i>Large button　+</button>
              <button class="btnNormal btnL nbd"><i class="i_language_dk"></i>Large button　+</button>
            </div>
          </li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="btnGrp">
    <div class="title">失效按鈕<br />(Disabled)</div>
    <ul>
      <li>
        <div class="title">Small</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnPrimary btnS" disabled><i class="i_language_dk"></i>Small button　+</button>
              <button class="btnPrimary btnS bd" disabled><i class="i_language_dk"></i>Small button　+</button>
              <button class="btnPrimary btnS nbd" disabled><i class="i_language_dk"></i>Small button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Normal</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnSecondary" disabled><i class="i_language_dk"></i>Normal button　+</button>
              <button class="btnSecondary bd" disabled><i class="i_language_dk"></i>Normal button　+</button>
              <button class="btnSecondary nbd" disabled><i class="i_language_dk"></i>Normal button　+</button>
            </div>
          </li>
        </ul>
      </li>
      <li>
        <div class="title">Large</div>
        <ul>
          <li>
            <div class="title">Default</div>
            <div class="btnBox">
              <button class="btnNormal btnL" disabled><i class="i_language_dk"></i>Large button　+</button>
              <button class="btnNormal btnL bd" disabled><i class="i_language_dk"></i>Large button　+</button>
              <button class="btnNormal btnL nbd" disabled><i class="i_language_dk"></i>Large button　+</button>
            </div>
          </li>
        </ul>
      </li>
    </ul>
  </div>
</div>

<!-- tabs:start -->

#### **HTML**

```html
<!-- 主要 -->
<button class="btnPrimary">button　+</button>
<!-- 次要 -->
<button class="btnSecondary">button　+</button>
<!-- 一般 -->
<button class="btnNormal">button　+</button>

<!-- 小按鈕 -->
<button class="btnPrimary btnS">button　+</button>
<!-- 正常按鈕 -->
<button class="btnPrimary">button　+</button>
<!-- 大按鈕 -->
<button class="btnPrimary btnL">button　+</button>

<!-- 加icon -->
<button class="btnPrimary"><i class="i_language_w"></i>button　+</button>
```

<!-- tabs:end -->
