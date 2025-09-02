# Flex system

?>格線系統：以 **flex** 為計算基礎，主要功能是分割欄位。

### 均分

?>每欄 **欄寬都相同** ，預設 2-12 欄。

> 算式： calc((100% - 間距 \* (欄數 - 1)) / 欄數);

<section>
          <div class="container">
            <h4>均分 2 欄</h4>
            <div class="flexTpl_2">
              <div class="col">
                <h3>title 1</h3>
                <p>col Lorem ipsum dolor sit amet, quos similique?</p>
              </div>
              <div class="col">
                <h3>title 2</h3>
                <p>col Lorem ipsum dolor sit</p>
              </div>
            </div>
          </div>
        </section>

<!-- tabs:start -->

### **css**

```css
//使用 mixin 的 itemWidth(間距, 欄位)
width: itemWidth(20, 2);
```

### **均分 2 欄**

```html
<div class="flexTpl_2">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### **均分 3 欄**

```html
<div class="flexTpl_3">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### **均分 4 欄**

```html
<div class="flexTpl_4">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### **均分 5 欄**

```html
<div class="flexTpl_5">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### **均分 6 欄**

```html
<div class="flexTpl_6">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

  <!-- tabs:end -->

### 自由分配

?> **每欄欄寬不相同**，加總等於`12`
可應用在**3+9**、**4+8**、**5+7**、**3+6+3** ...等非均分的分割。

<section>
          <div class="container">
            <h3>flexTpl_3_6_3</h3>
            <div class="flexTpl_3_6_3">
              <div class="col">
                <h3>次標題一</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quo facilis sequi quidem velit quae voluptas temporibus aliquam quasi doloremque sunt? Sapiente ea dolorem dolore sit itaque facere sunt voluptatem deleniti!</p>
              </div>
              <div class="col">
                <h3>次標題二</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quo facilis sequi quidem velit quae voluptas temporibus aliquam quasi doloremque sunt? Sapiente ea dolorem dolore sit itaque facere sunt voluptatem deleniti!</p>
              </div>
              <div class="col">
                <h3>次標題三</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quo facilis sequi quidem velit quae voluptas temporibus aliquam quasi doloremque sunt? Sapiente ea dolorem dolore sit itaque facere sunt voluptatem deleniti!</p>
              </div>
            </div>
          </div>
        </section>

目前已有預設幾種分割方式

<!-- tabs:start -->

### **css**

```css
//使用 mixin 的 flexWidth(間距, 佔幾份，加總為12即可)
.col {
  &:nth-child(1) {
    width: flexWidth(20, 8);
  }
  &:nth-child(2) {
    width: flexWidth(20, 4);
  }
}
```

### ** 8+4 **

```html
<div class="flexTpl_8_4">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 4+8 **

```html
<div class="flexTpl_4_8">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 9+3 **

```html
<div class="flexTpl_9_3">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 3+9 **

```html
<div class="flexTpl_3_9">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 7+5 **

```html
<div class="flexTpl_7_5">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 5+7 **

```html
<div class="flexTpl_5_7">
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 3+3+6 **

```html
<div class="flexTpl_3_3_6">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 3+6+3 **

```html
<div class="flexTpl_3_6_3">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 6+3+3 **

```html
<div class="flexTpl_6_3_3">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 2+2+8 **

```html
<div class="flexTpl_2_2_8">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 2+8+2 **

```html
<div class="flexTpl_2_8_2">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### ** 8+2+2 **

```html
<div class="flexTpl_8_2_2">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

<!-- tabs:end -->

### 混合運用

?> **均分** Ｘ **自由分配**

<section>
    <div class="container">
      <div class="flexTpl_2">
        <div class="col">
          <div class="flexTpl_4_8">
            <div class="col">
              <div class="pic"><img src="https://hywebu00.github.io/hyui_flex/images/demo/01.jpg" /></div>
            </div>
            <div class="col">
              <div class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum nam, aperiam error accusamus, distinctio laboriosam minus nesciunt cum labore voluptate consectetur magni, illum in recusandae. Optio, ab voluptatibus suscipit magnam.</div>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="flexTpl_4_8">
            <div class="col">
              <div class="pic"><img src="https://hywebu00.github.io/hyui_flex/images/demo/01.jpg" /></div>
            </div>
            <div class="col">
              <div class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum nam, aperiam error accusamus, distinctio laboriosam minus nesciunt cum labore voluptate consectetur magni, illum in recusandae. Optio, ab voluptatibus suscipit magnam.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
</section>

<!-- tabs:start -->

### **HTML**

```html
<div class="flexTpl_2">
  <div class="col">
    <div class="flexTpl_4_8">
      <div class="col"></div>
      <div class="col"></div>
    </div>
  </div>
  <div class="col">
    <div class="flexTpl_4_8">
      <div class="col"></div>
      <div class="col"></div>
    </div>
  </div>
</div>
```

<!-- tabs:end -->

<style>
  .container{
    display:block !important; 
  }
    .col{
      padding:20px;
      background-color:#ededed;
      .col{
        padding:0px;
        background:none;
      }
    }
    .col p , .col h3{
        color:#777;
    }
    h4{
    margin-bottom: 0.5em;
    }
    [class*="flexTpl"] h3{
        margin-top:0em;
    }
    .text{
         color:#777;
    }
</style>
