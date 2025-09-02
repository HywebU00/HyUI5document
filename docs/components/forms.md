# Forms 表單

?>相關 css：scss/components/`_form.scss`

## 基本結構

!>表單外層以 `<form class="formBox"></form>`包覆，為符合無障礙標準須加上`<label></label>`，但是不想要在畫面上出現文字時，加上 className `srOnly`隱藏 label 文字

每一項都會以`formList`包住，內部至少一個`label`和`input`/`select`/`textarea`皆由`formContent`包著。

`label`的`for=""`要對應到`input`的`id`。

**多層**或是**一個項目有多個輸入**的情況下使用`fieldset`和`legend`，目的在於可以更明確的讓無障礙使用者知道層級或是群組內容。

`fieldset`和`legend`的用法

```html
<fieldset>
  <legend>地址</legend>
  <label>縣市</label>
  <input type="text" />
  <label>區域</label>
  <input type="text" />
</fieldset>
```

套用 HyUI 的用法

<!-- tabs:start -->

#### **一般 HTML**

一般的情況下使用

```html
<form class="formBox">
  <div class="formList">
    <legend class="formListTitle" id="abc">標題</legend>
    <div class="formContent">...</div>
  </div>
</form>
```

#### **多組項目 HTML**

```html
<form class="formBox">
  <fieldset class="formList" aria-labelledby="abc">
    <legend class="formListTitle" id="abc">區塊標題</legend>
    <div class="formContent"></div>
  </fieldset>
</form>

<!-- 或是 -->

<form class="formBox">
  <fieldset class="formList" aria-labelledby="abc">
    <legend class="formListTitle" id="abc">區塊標題</legend>
    <div class="formContent">
      <div class="formList">
        <legend class="formListTitle" id="abc">標題</legend>
        <div class="formContent">...</div>
      </div>
    </div>
  </fieldset>
</form>
```

<!-- tabs:end -->

### formContent

若有多筆填寫項目或需要其他內容則需要使用`formContent`包住，並也可加上。

**範例**

<form class="formBox">
<fieldset class="formList" aria-labelledby="fieldset1">
  <legend class="formListTitle" id="fieldset1">Title</legend>
  <div class="formContent inline noFull">
    <label for="formItem1" class="srOnly">輸入文字：</label>
    <input type="text" name="" id="formItem1" placeholder="請輸入文字" />
    <div class="select">
      <label for="formItem1Select" class="srOnly">選擇項目：</label>
      <select name="" id="formItem1Select">
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
  </div>
</fieldset>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<fieldset class="formList" aria-labelledby="fieldset1">
  <legend class="formListTitle" id="fieldset1">Title</legend>
  <div class="formContent inline noFull">
    <label for="formItem1" class="srOnly">輸入文字：</label>
    <input type="text" name="" id="formItem1" placeholder="請輸入文字" />
    <div class="select">
      <label for="formItem1Select" class="srOnly">選擇項目：</label>
      <select name="" id="formItem1Select">
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
  </div>
</fieldset>
```

<!-- tabs:end -->

表單也可以使用`Flex system`功能，`formContent`中包入即可

### inline

表單內容需要並排的時候若不確定表單內容寬度可以用`inline`在讓內容並排，使用後除`label`以外都會填滿內容。  
若不希望填滿內容則須在增加`noFull`，請注意增加 class 的位置。

**範例**

<form class="formBox">
<div class="formList inline">
  <label class="formListTitle" for="">帳號</label>
  <div class="formContent">
    <input type="text" name="username" id="" placeholder="請輸入帳號">
  </div>
</div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList inline"></div>
```

<!-- tabs:end -->

### noFull

若不希望`label`以外都會填滿內容則須增加`noFull`，請注意增加 class 的位置，`formList`和`formContent`皆可增加。

**範例**

<form class="formBox">
<div class="formList inline noFull">
  <label class="formListTitle" for="">帳號</label>
  <div class="formContent">
    <input type="text" name="username" id="" placeholder="請輸入帳號">
  </div>
</div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList inline noFull"></div>
```

<!-- tabs:end -->

## 狀態

### 必填

`formList` 加上 `.required`  
`input`/`select`/`textarea`也要加上`required`

**範例**

<form class="formBox">
  <div class="formList required">
    <label class="formListTitle" for="">必填</label>
    <div class="formContent">
      <input type="text" name="" id="" placeholder="請輸入文字" required />
    </div>
  </div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList required">
  <input type="text" required />
</div>
```

<!-- tabs:end -->

### 錯誤狀態

`formList` 加上 `.error`。

**範例**

<form class="formBox">
  <div class="formList error">
    <label class="formListTitle" for="">錯誤狀態</label>
    <div class="formContent">
      <input type="text" name="" id="" placeholder="請輸入文字" />
    </div>
  </div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList error"></div>
```

<!-- tabs:end -->

### Disabled

`input`/`select`/`textarea` 加上 `disabled`。

**範例**

<form class="formBox">
  <div class="formList">
    <div class="formContent">
      <input type="text" name="" id="" placeholder="請輸入文字" disabled />
      <div class="inputOption">
        <input type="radio" name="" id="radioenable1" value="enable" disabled />
        <label for="radioenable1">Enable</label>
      </div>
      <div class="inputOption">
        <input type="checkbox" name="" id="radioGrp1enable1" value="enable" disabled />
        <label for="radioGrp1enable1">Enable</label>
      </div>
      <div class="select">
        <select name="" id="formItem4Select" disabled>
          <option value="">請選擇</option>
          <option value="option">option</option>
          <option value="option">option</option>
        </select>
      </div>
      <textarea disabled></textarea>
    </div>
  </div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<input type="text" disabled />
<input type="radio" disabled />
<input type="checkBox" disabled />
<select disabled></select>
<textarea disabled></textarea>
```

<!-- tabs:end -->

### Checked

只有在`input[type="radio"]`、`input[type="checkBox"]`加上 `checked`。

**範例**

<form class="formBox">
  <div class="formList">
    <div class="formContent">
      <div class="inputOption">
        <input type="radio" name="" id="radioenable1" value="enable" checked />
        <label for="radioenable1">Enable</label>
      </div>
      <div class="inputOption">
        <input type="checkbox" name="" id="radioGrp1enable1" value="enable" checked />
        <label for="radioGrp1enable1">Enable</label>
      </div>
    </div>
  </div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<input type="radio" checked /> <input type="checkBox" checked />
```

<!-- tabs:end -->

## 表單元件

!> `label`需要增加`for`對應到`input`/`select`/`textarea`的 `id`。

```html
<label for="targetId">文字</label> <input type="text" id="targetId" />
```

### 文字

**範例**

<form class="formBox">
<div class="formList required">
  <label class="formListTitle" for="targetId1">文字</label>
  <div class="formContent">
    <input type="text" name="" id="targetId1" placeholder="請輸入文字" required />
  </div>
</div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="formList required">
  <label class="formListTitle" for="targetId1">一般狀態 + 顯示提示文字</label>
  <div class="formContent">
    <input type="text" name="" id="targetId1" placeholder="請輸入文字" required />
  </div>
</div>
```

<!-- tabs:end -->

#### 前方 + icon

**範例**

<form class="formBox">
  <div class="formList">
    <label class="formListTitle" for="targetId2">文字</label>
    <div class="formContent">
    <div class="inputBox">
      <i class="i_lock_dk"></i>
      <input type="text" name="" id="targetId2" placeholder="請輸入文字" />
      </div>
    </div>
  </div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="formList">
  <label class="formListTitle" for="targetId2">文字</label>
  <div class="formContent">
    <div class="inputBox">
      <i class="i_lock_dk"></i>
      <input type="text" name="" id="targetId2" placeholder="請輸入文字" />
    </div>
  </div>
</div>
```

<!-- tabs:end -->
<!-- tabs:end -->

#### 後方 + icon

**範例**

<form class="formBox">
  <div class="formList">
    <label class="formListTitle" for="targetId3">文字</label>
    <div class="formContent">
      <div class="inputBox">
        <input type="text" name="" id="targetId3" placeholder="請輸入文字" />
        <i class="i_lock_dk"></i>
      </div>
    </div>
  </div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<form class="formBox">
  <div class="formList">
    <label class="formListTitle" for="targetId3">文字</label>
    <div class="formContent">
      <div class="inputBox">
        <input type="text" name="" id="targetId3" placeholder="請輸入文字" />
        <i class="i_lock_dk"></i>
      </div>
    </div>
  </div>
</form>
```

<!-- tabs:end -->

### 密碼

**範例**

<form class="formBox">
  <div class="formList">
    <label class="formListTitle" for="targetId4">密碼</label>
    <div class="formContent">
      <div class="inputBox">
        <i class="i_lock_dk"></i>
        <input class="password" type="password" name="" id="targetId4" autocomplete="current-password" placeholder="請輸入密碼" />
        <button type="button" class="formEyes" data-show="顯示密碼" data-hide="隱藏密碼" aria-label="顯示密碼" aria-pressed="false"></button>
      </div>
      <div role="alert" id="alert1">
                          <div class="formNotice">
                            <span>這是一般提醒訊息區塊</span>
                          </div>
                          <div class="formNoticeInfo">
                            <span>這是一般提醒訊息區塊</span>
                          </div>
                          <div class="formNoticeSuccess">
                            <span>您已成功登入</span>
                          </div>
                          <div class="formNoticeWarning">
                            <span>這似乎不是一個正常的Email格式</span>
                          </div>
                          <div class="formNoticeError">
                            <span>您輸入的帳號密碼有誤！</span>
                          </div>
                        </div>
    </div>
  </div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList inline">
  <label class="formListTitle" for="targetId4">密碼</label>
  <div class="formContent">
    <div class="inputBox">
      <i class="i_lock_dk"></i>
      <input class="password" type="password" name="" id="targetId4" autocomplete="current-password" placeholder="請輸入密碼" />
      <button class="formEyes" type="button" data-show="顯示密碼" data-hide="隱藏密碼"></button>
    </div>
    <div class="formNotice">
      <span>這是一般提醒訊息區塊</span>
      <button type="button" class="noticeClose" aria-label="關閉提醒"></button>
    </div>
    <div class="formNoticeInfo">
      <span>這是一般提醒訊息區塊</span>
      <button type="button" class="noticeClose" aria-label="關閉提醒"></button>
    </div>
    <div class="formNoticeSuccess">
      <span>您已成功登入</span>
      <button type="button" class="noticeClose" aria-label="關閉提醒"></button>
    </div>
    <div class="formNoticeWarning">
      <span>這似乎不是一個正常的Email格式</span>
      <button type="button" class="noticeClose" aria-label="關閉提醒"></button>
    </div>
    <div class="formNoticeError">
      <span>您輸入的帳號密碼有誤！</span>
      <button type="button" class="noticeClose" aria-label="關閉提醒"></button>
    </div>
  </div>
</div>
```

<!-- tabs:end -->

### 日期

**type="date" 範例**

<form class="formBox">
<div class="formList" aria-labelledby="fieldset6">
  <label for="startDate1" class="srOnly">出生年月日</label>
  <div class="formContent">
    <input type="date" name="" id="startDate1" />
  </div>
</div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList" aria-labelledby="fieldset6">
  <label for="startDate1" class="srOnly">出生年月日</label>
  <div class="formContent">
    <input type="date" name="" id="startDate1" />
  </div>
</div>
```

<!-- tabs:end -->

**select 範例**

<form class="formBox">
<fieldset class="formList" aria-labelledby="fieldset10">
  <legend class="formListTitle" id="fieldset10">出生年月日</legend>
  <div class="formContent inline">
    <div class="select">
      <select name="" id="formItem5Select" required>
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
    <label for="formItem5Select">年</label>
    <div class="select">
      <select name="" id="formItem6Select" required>
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
    <label for="formItem6Select">月</label>
    <div class="select">
      <select name="" id="formItem7Select" required>
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
    <label for="formItem7Select">日</label>
  </div>
</fieldset>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<fieldset class="formList" aria-labelledby="fieldset10">
  <legend class="formListTitle" id="fieldset10">出生年月日</legend>
  <div class="formContent inline">
    <div class="select">
      <select name="" id="formItem5Select" required>
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
    <label for="formItem5Select">年</label>
    <div class="select">
      <select name="" id="formItem6Select" required>
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
    <label for="formItem6Select">月</label>
    <div class="select">
      <select name="" id="formItem7Select" required>
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
    <label for="formItem7Select">日</label>
  </div>
</fieldset>
```

<!-- tabs:end -->

### 下拉選單

下拉選單需要`.select`包起。

**範例**

<form class="formBox">
<div class="formList">
  <label class="formListTitle" for="targetId5">下拉選單</label>
  <div class="formContent">
    <div class="select">
      <select name="" id="targetId5">
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
  </div>
</div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList">
  <label class="formListTitle" for="targetId5">下拉選單</label>
  <div class="formContent">
    <div class="select">
      <select name="" id="targetId5">
        <option value="">請選擇</option>
        <option value="option">option</option>
        <option value="option">option</option>
      </select>
    </div>
  </div>
</div>
```

<!-- tabs:end -->

### 下拉選單 - 群組

下拉選單需要`.select`包起。

**範例**

<form class="formBox">
<div class="formList">
  <label class="formListTitle" for="targetId5">下拉選單</label>
  <div class="formContent">
    <div class="select">
      <select name="" id="formItem2Select">
        <option value="">請選擇</option>
        <optgroup label="選項群組一二三">
          <option value="">選項一</option>
          <option value="">選項二</option>
          <option value="">選項三</option>
        </optgroup>
        <optgroup label="選項群組ABC">
          <option value="">選項Ａ</option>
          <option value="">選項Ｂ</option>
          <option value="">選項Ｃ</option>
        </optgroup>
      </select>
    </div>
  </div>
</div>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<div class="formList">
  <label class="formListTitle" for="targetId5">下拉選單</label>
  <div class="formContent">
    <div class="select">
      <select name="" id="formItem2Select">
        <option value="">請選擇</option>
        <optgroup label="選項群組一二三">
          <option value="">選項一</option>
          <option value="">選項二</option>
          <option value="">選項三</option>
        </optgroup>
        <optgroup label="選項群組ABC">
          <option value="">選項Ａ</option>
          <option value="">選項Ｂ</option>
          <option value="">選項Ｃ</option>
        </optgroup>
      </select>
    </div>
  </div>
</div>
```

<!-- tabs:end -->

### 單選核取

由於`type="radio"`常常是多組出現，顧需要使用`fieldset`以及`legend`將選項包住供無障礙能正確的判斷。

**範例**

<form class="formBox">
<fieldset class="formList inline">
  <legend class="formListTitle">水平單選核取表單</legend>
  <div class="formContent inline">
    <div class="inputOption">
      <input type="radio" name="radioGrp1" id="RE1" value="enable" />
      <label for="RE1">Enable</label>
    </div>
    <div class="inputOption">
      <input type="radio" name="radioGrp1" id="RD1" value="disable" disabled />
      <label for="RD1">Disable</label>
    </div>
    <div class="inputOption">
      <input type="radio" name="radioGrp1" id="RC1" value="checked" checked />
      <label for="RC1">Checked</label>
    </div>
  </div>
</fieldset>

</form>

<!-- tabs:start -->

#### **HTML**

```html
<fieldset class="formList inline">
  <legend class="formListTitle">水平單選核取表單</legend>
  <div class="formContent inline">
    <div class="inputOption">
      <input type="radio" name="radioGrp1" id="RE1" value="enable" />
      <label for="RE1">Enable</label>
    </div>
    <div class="inputOption">
      <input type="radio" name="radioGrp1" id="RD1" value="disable" disabled />
      <label for="RD1">Disable</label>
    </div>
    <div class="inputOption">
      <input type="radio" name="radioGrp1" id="RC1" value="checked" checked />
      <label for="RC1">Checked</label>
    </div>
  </div>
</fieldset>
```

<!-- tabs:end -->

### 複選核取表單

同`type="radio"`常常是多組出現，顧也需要使用`fieldset`將選項包住以及使用`legend`告知標題供無障礙能正確的判斷。

**範例**

<form class="formBox">
<fieldset class="formList inline">
  <legend class="formListTitle">水平複選核取表單</legend>
  <div class="formContent inline">
    <div class="inputOption">
      <input type="checkbox" name="checkboxGrp1" id="CE1" value="enable" />
      <label for="CE1">Enable</label>
    </div>
    <div class="inputOption">
      <input type="checkbox" name="checkboxGrp1" id="CD1" value="disable" disabled />
      <label for="CD1">Disable</label>
    </div>
    <div class="inputOption">
      <input type="checkbox" name="checkboxGrp1" id="CC1" value="checked" checked />
      <label for="CC1">checked</label>
    </div>
  </div>
</fieldset>
</form>

<!-- tabs:start -->

#### **HTML**

```html
<fieldset class="formList inline">
  <legend class="formListTitle">水平複選核取表單</legend>
  <div class="formContent inline">
    <div class="inputOption">
      <input type="checkbox" name="checkboxGrp1" id="CE1" value="enable" />
      <label for="CE1">Enable</label>
    </div>
    <div class="inputOption">
      <input type="checkbox" name="checkboxGrp1" id="CD1" value="disable" disabled />
      <label for="CD1">Disable</label>
    </div>
    <div class="inputOption">
      <input type="checkbox" name="checkboxGrp1" id="CC1" value="checked" checked />
      <label for="CC1">checked</label>
    </div>
  </div>
</fieldset>
```

<!-- tabs:end -->

### 檔案上傳

多檔上傳只需要在`input`中新增`multiple`即可。

**單檔範例**

<form class="formBox">
<div class="formList">
  <label class="formListTitle" for="formItem12">檔案上傳</label>
  <div class="formContent">
    <div class="inputFile">
      <div class="fileName"></div>
      <div class="uploadStyle btnPrimary">請選擇檔案</div>
      <input class="downloadFile" type="file" name="text" id="formItem12" placeholder="請選擇檔案" />
    </div>
  </div>
</div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="formList inline">
  <label class="formListTitle" for="formItem12">單檔上傳</label>
  <div class="formContent">
    <div class="inputFile">
      <div class="fileName">請選擇檔案</div>
      <div class="uploadStyle btnPrimary">請選擇檔案</div>
      <input class="downloadFile" type="file" name="text" id="formItem12" placeholder="請選擇檔案" />
    </div>
  </div>
</div>
```

<!-- tabs:end -->

### 多行文字表單

<form class="formBox">
<div class="formList">
  <label class="formListTitle" for="">標題</label>
  <div class="formContent">
    <textarea id="" rows="3"></textarea>
  </div>
</div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="formList">
  <label class="formListTitle" for="">標題</label>
  <div class="formContent">
    <textarea id="" rows="3"></textarea>
  </div>
</div>
```

<!-- tabs:end -->

### 下方按鈕區塊

<form class="formBox">
<div class="formBtnBox">
  <button class="btnSecondary" type="reset">清除</button>
  <button class="btnPrimary" type="submit">送出</button>
</div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="formBtnBox">
  <button class="btnSecondary" type="reset">清除</button>
  <button class="btnPrimary" type="submit">送出</button>
</div>
```

<!-- tabs:end -->

## 表單排版

使用`gridBox`包著內容。

### 格線式表單

<form class="formBox">
<div class="gridBox">
  <div class="formList inline">
    <label class="formListTitle" for="formItem7">帳號</label>
<div class="formBtnBox">
    <input type="text" name="username" id="formItem7" autocomplete="username" placeholder="請輸入帳號" required />
</div>
  </div>
  <fieldset class="formList inline">
    <legend class="formListTitle">起始日期</legend>
    <div class="formContent inline">
      <label for="startDate2" class="srOnly">開始日期</label>
      <input type="date" name="" id="startDate2" />
      <span>—</span>
      <label for="endDate2" class="srOnly">結束日期</label>
      <input type="date" name="" id="endDate2" />
    </div>
  </fieldset>
  <fieldset class="formList inline">
    <legend class="formListTitle">水平單選核取表單</legend>
    <div class="formContent inline">
      <div class="inputOption">
        <input type="radio" name="radioGrp3" id="RD3" value="disable" disabled />
        <label for="RD3">Disable</label>
      </div>
      <div class="inputOption">
        <input type="radio" name="radioGrp3" id="RC3" value="checked" />
        <label for="RC3">Checked</label>
      </div>
      <div class="inputOption">
        <input type="radio" name="radioGrp3" id="RCD3" value="checkedDisabled" checked disabled />
        <label for="RCD3">Checked:disable</label>
      </div>
    </div>
  </fieldset>
</div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="gridBox">
  <div class="formList inline">
    <label class="formListTitle" for="formItem7">帳號</label>
    <div class="formContent">
      <input type="text" name="username" id="formItem7" autocomplete="username" placeholder="請輸入帳號" required />
    </div>
    </div>
    <fieldset class="formList inline">
      <legend class="formListTitle">起始日期</legend>
      <div class="formContent inline">
        <label for="startDate2" class="srOnly">開始日期</label>
        <input type="date" name="" id="startDate2" />
        <span>—</span>
        <label for="endDate2" class="srOnly">結束日期</label>
        <input type="date" name="" id="endDate2" />
      </div>
    </fieldset>
    <fieldset class="formList inline">
      <legend class="formListTitle">水平單選核取表單</legend>
      <div class="formContent inline">
        <div class="inputOption">
          <input type="radio" name="radioGrp3" id="RD3" value="disable" disabled />
          <label for="RD3">Disable</label>
        </div>
        <div class="inputOption">
          <input type="radio" name="radioGrp3" id="RC3" value="checked" />
          <label for="RC3">Checked</label>
        </div>
        <div class="inputOption">
          <input type="radio" name="radioGrp3" id="RCD3" value="checkedDisabled" checked disabled />
          <label for="RCD3">Checked:disable</label>
        </div>
      </div>
    </fieldset>
  </div>
</div>
```

<!-- tabs:end -->

### 多層次表單

<form class="formBox">
<div class="gridBox">
  <fieldset class="formList inline">
    <legend class="formListTitle">個人資料</legend>
    <div class="formContent">
      <div class="formList inline required">
        <label class="formListTitle" for="formItem14">姓名</label>
        <input type="text" name="" id="formItem14" autocomplete="name" placeholder="" required />
      </div>
      <fieldset class="formList inline required">
        <legend class="formListTitle">性別</legend>
        <div class="formContent inline">
          <div class="inputOption">
            <input type="radio" name="genderGrp" id="male" />
            <label for="male">男</label>
          </div>
          <div class="inputOption">
            <input type="radio" name="genderGrp" id="female" />
            <label for="female">女</label>
          </div>
        </div>
      </fieldset>
      <div class="formList inline required">
        <label class="formListTitle" for="formItem15">出生年月日</label>
        <div class="formContent">
        <input type="date" name="" id="formItem15" required />
      </div>
      </div>
    </div>
  </fieldset>
  <fieldset class="formList inline">
    <legend class="formListTitle">聯絡方式</legend>
    <div class="formContent">
      <div class="formList inline">
        <label class="formListTitle" for="formItem8Select">國家區域</label>
        <div class="formContent">
        <div class="select">
          <select name="" id="formItem8Select">
            <option value="">請選擇</option>
            <option value="option">option</option>
            <option value="option">option</option>
          </select>
      </div>
        </div>
      </div>
      <fieldset class="formList inline" aria-labelledby="fieldset12">
        <legend class="formListTitle" id="fieldset12">電話號碼</legend>
        <div class="formContent">
          <div class="flexTpl_3_9">
            <div class="col">
              <label for="formItem16" class="srOnly">區碼</label>
              <input type="text" id="formItem16" aria-label="區碼" />
            </div>
            <div class="col">
              <label for="formItem17" class="srOnly">號碼</label>
              <input type="text" id="formItem17" aria-label="號碼" />
            </div>
          </div>
        </div>
      </fieldset>
      <div class="formList inline">
        <label class="formListTitle" for="formItem18">E-mail</label>
        <div class="formContent">
          <div class="inputBox">
            <i class="i_email_dk"></i>
            <input type="email" name="email" id="formItem18" autocomplete="email" placeholder="請輸入電子信箱" />
          </div>
        </div>
      </div>
      <fieldset class="formList inline" aria-labelledby="fieldset13">
        <legend class="formListTitle" id="fieldset13">聯絡地址</legend>
        <div class="formContent">
          <div class="flexTpl_2_2_8">
            <div class="col">
              <div class="select">
                <label for="formItem9Select" class="srOnly">縣市</label>
                <select name="" id="formItem9Select">
                  <option value="">請選擇</option>
                  <option value="option">option</option>
                  <option value="option">option</option>
                </select>
              </div>
            </div>
            <div class="col">
              <div class="select">
                <label for="formItem10Select" class="srOnly">縣市</label>
        <div class="formContent">
                <select name="" id="formItem10Select">
                  <option value="">請選擇</option>
                  <option value="option">option</option>
                  <option value="option">option</option>
                </select>
              </div>
            </div>
            </div>
            <div class="col">
              <label for="formItem19" class="srOnly">聯絡地址</label>
        <div class="formContent">
              <input type="text" aria-label="聯絡地址" id="formItem19" name="" />
            </div>
            </div>
          </div>
        </div>
      </fieldset>
    </div>
  </fieldset>
</div>
</form>
<!-- tabs:start -->

#### **HTML**

```html
<div class="gridBox">
  <fieldset class="formList inline">
    <legend class="formListTitle">個人資料</legend>
    <div class="formContent">
      <div class="formList inline required">
        <label class="formListTitle" for="formItem14">姓名</label>
        <input type="text" name="" id="formItem14" autocomplete="name" placeholder="" required />
      </div>
      <fieldset class="formList inline required">
        <legend class="formListTitle">性別</legend>
        <div class="formContent inline">
          <div class="inputOption">
            <input type="radio" name="genderGrp" id="male" />
            <label for="male">男</label>
          </div>
          <div class="inputOption">
            <input type="radio" name="genderGrp" id="female" />
            <label for="female">女</label>
          </div>
        </div>
      </fieldset>
      <div class="formList inline required">
        <label class="formListTitle" for="formItem15">出生年月日</label>
        <div class="formContent">
          <input type="date" name="" id="formItem15" required />
        </div>
      </div>
    </div>
  </fieldset>
  <fieldset class="formList inline">
    <legend class="formListTitle">聯絡方式</legend>
    <div class="formContent">
      <div class="formList inline">
        <label class="formListTitle" for="formItem8Select">國家區域</label>
        <div class="formContent">
          <div class="select">
            <select name="" id="formItem8Select">
              <option value="">請選擇</option>
              <option value="option">option</option>
              <option value="option">option</option>
            </select>
          </div>
        </div>
      </div>
      <fieldset class="formList inline" aria-labelledby="fieldset12">
        <legend class="formListTitle" id="fieldset12">電話號碼</legend>
        <div class="formContent">
          <div class="flexTpl_3_9">
            <div class="col">
              <label for="formItem16" class="srOnly">區碼</label>
              <input type="text" id="formItem16" aria-label="區碼" />
            </div>
            <div class="col">
              <label for="formItem17" class="srOnly">號碼</label>
              <input type="text" id="formItem17" aria-label="號碼" />
            </div>
          </div>
        </div>
      </fieldset>
      <div class="formList inline">
        <label class="formListTitle" for="formItem18">E-mail</label>
        <div class="formContent">
          <div class="inputBox">
            <i class="i_email_dk"></i>
            <input type="email" name="email" id="formItem18" autocomplete="email" placeholder="請輸入電子信箱" />
          </div>
        </div>
      </div>
      <fieldset class="formList inline" aria-labelledby="fieldset13">
        <legend class="formListTitle" id="fieldset13">聯絡地址</legend>
        <div class="formContent">
          <div class="flexTpl_2_2_8">
            <div class="col">
              <div class="select">
                <label for="formItem9Select" class="srOnly">縣市</label>
                <select name="" id="formItem9Select">
                  <option value="">請選擇</option>
                  <option value="option">option</option>
                  <option value="option">option</option>
                </select>
              </div>
            </div>
            <div class="col">
              <div class="select">
                <label for="formItem10Select" class="srOnly">縣市</label>
                <div class="formContent">
                  <select name="" id="formItem10Select">
                    <option value="">請選擇</option>
                    <option value="option">option</option>
                    <option value="option">option</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="col">
              <label for="formItem19" class="srOnly">聯絡地址</label>
              <div class="formContent">
                <input type="text" aria-label="聯絡地址" id="formItem19" name="" />
              </div>
            </div>
          </div>
        </div>
      </fieldset>
    </div>
  </fieldset>
</div>
```

<!-- tabs:end -->
