## scss 架構

?>scss 架構簡介：
全站的美容設計寶典。

```text
├── scss/
   ├── basic/                          // 基本設定資料夾
   │   ├── _accessibility.scss         // 無障礙外框設定
   │   ├── _default.scss               // 通用設定
   │   ├── _flexTemplate.scss          // 版面配置
   │   ├── _fontfamily.scss            // 字型設定
   │   ├── _mixin.scss                 // scss @mixin/@function檔
   │   ├── _normalize.scss             // 統一瀏覽器樣式
   │   └── _print.scss                 // 列印
   │
   ├── pages/
   │   ├── _404.scss.scss              // 404頁
   │   ├── _cp.scss                    // 內容頁
   │   ├── _lp.scss                    // 列表頁
   │   ├── _mp.scss                    // 首頁
   │   ├── _np.scss                    // 節點頁
   │   └── _sitemap.scss               // sitemap
   │
   ├── components/                     // 元件資料夾
   │   ├── _accordion.scss             // 手風琴
   │   ├── _breadcrumb.scss            // 麵包屑
   │   ├── _button.scss                // 按鈕
   │   ├── _download.scss              // 下載
   │   ├── _fatFooter.scss             // footer選單
   │   ├── _floatNav.scss              // 側邊浮動區塊
   │   ├── _fontSize.scss              // 字體縮放
   │   ├── _form.scss                  // 表單
   │   ├── _functionPanel.scss         // 內頁功能列
   │   ├── _icon.scss                  // icon
   │   ├── _language.scss              // 上方語系選單
   │   ├── _menu.scss                  // 主選單
   │   ├── _pagination.scss            // 分頁
   │   ├── _popup.scss                 // 燈箱/彈跳區塊
   │   ├── _search.scss                // 上方搜尋
   │   ├── _share.scss                 // 分享
   │   ├── _sideNav.scss               // 側邊選單
   │   ├── _slider.scss                // swiper輪播設定
   │   ├── _table.scss                 // 表格
   │   ├── _tabs.scss                  // 頁籤
   │   ├── _tag.scss                   // 標籤
   │   └── _topNav.scss                // 上方選單
   │
   ├── template/                       // 基本模板共用scss
   │   ├── _footer.scss                // footer通用設置
   │   ├── _header.scss                // header通用設置
   │   └── _main.scss                  // main通用設置
   │
   ├── theme/                          // 顏色資料夾
   │   └── _blue.scss                  // 藍色
   │
   ├── _variable.scss                  // 資全站樣式定義
   └── style.scss                      // 統一匯出之主要SCSS


```

## [\_mixin.scss](quickStart/mixin.md)

可查詢常用的 **＠extend**、 **@include** 使用方式。

---

## \_variable.scss

全站的 **基本定義**，**顏色**、**字型**...等。

---
