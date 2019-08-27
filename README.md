# about-sass
可參考
https://www.html.cn/doc/sass/#nested-properties
https://sass-lang.com/guide
https://www.w3schools.com/sass/


# 将 Sass 转换为 SCSS
$ sass-convert style.sass style.scss

# 将 SCSS 转换为 Sass
$ sass-convert style.scss style.sass

# 在命令行中运行 Sass ,只要输入
sass input.scss output.css

# 編譯目錄中的 scss 檔案到另一個目錄 CSS 時
sass --update scss:css

# 监视文件的改动并更新 CSS
sass --watch input.scss:output.css

# 引用父選擇符： &

# 使用 $ 來表示變數

# pseudo 偽元素 ::before、::after、:hover

# 跨瀏覽器的 prefix @mixin @include 

# Variables/Nesting/Mixins/Functions/Operations

# 變數與運算Variables
($)來定義變數 用連接號(-)與全小寫英文 如$second-color
1.對於會套用到整個網站的每個顏色、字體建議都先定義成變數。
2.使用 16 進位碼來定義來指定顏色 #ff0000。
3.變數可以再進行作加減乘除餘(+-*/%)運算，最特別的是字串與顏色色碼也可以進行運算。
4.進行運算的運算符號前後要加上空格，不要黏在一團。

# 巢狀Nesting
1.在某個 DOM 元素之內，有空格如 ul li a
2.同個 DOM 元素的但不同類別，沒有空格如 ul.mylist或a:hover，需要加入與符號(&)來定義
3.如果你有像h1.title或li.mylist之類的 CSS 宣告，不論裡面的樣式有多簡單，都應該在 SCSS 檔案中都要列成巢狀結構。
4.變量範圍變數可以設定在特定的巢狀級別內
5.!global設定全局的變量(類似!important的用法)，最好是定義在所有規則之外例如另外的檔案用@include進來
6.Nested Rules / Properties

# 匯入Import
1.@import指令允許您將一個文件的內容包含在另一個文件中。
2.Sass @import 指令包含CSS中的文件; 所以在運行時不需要額外的HTTP調用！
3.您不需要指定文件擴展名，Sass會自動假定您指的是.sass或.scss文件。您還可以導入CSS文件。該@import 指令導入文件，然後可以在主文件中使用導入文件中定義的任何變量或mixins。
4.Sass有一個機制：如果你用下劃線開始文件名，Sass就不會對它進行轉換。@import "colors"導入文件“_colors.scss”(此文件不會直接轉換為“colors.css”）
5.Don't Repeat Youself，將相關的代碼保存在單獨的文件中，reset,variables,colors,fonts,font-sizes,etc.

# 混合Mixins
1.混合(Mixin)有點像函式或一群值的組合，可以輸入一個值然後套用這個值的整串結果。@mixin指令允許您創建要在整個網站中重用的CSS代碼。
2.@minix標記需要對應到@include標記。Sass中的連字符和下劃線的提示：連字符和下劃線被認為是相同的。這意味著@mixin important-text {}和@mixin important_text {}被認為是相同的mixin！
3.整個群組或整個類別的 CSS 套用，如 CSS3 很多新的定義都會有供應商前綴字的問題，網路上也有很多現成的混合庫可以使用，例如以下三種常見的函式庫，但這裡面也不只有混合(Mixin)而已，還有很多其他的內容，直接使用可以節省時間，三種基本上都使用gem來安裝:
Bourbon: bourbon.io
Compass: compass-style.org
Susy: susy.oddbird.net

# 擴充/繼承Extend
1.擴充(Extend)是可以擴充原有的 CSS 類別定義，你可以再加上不同的定義或覆蓋原有的定義。
2.不需要原來繼承的 CSS 類別，可使用佔位符(%)保留繼承該類別的設定。
3.擴充(Extend)的用法相當簡單，相較於混合(Mixin)它不能傳入值，而且會合併相同的定義在同一個類別之中。

# 函式(Functions)
1.可以定義自訂的函式
2.@return、@if、@for、@each等流程控制。
3.內建了許多工具函式，如按比例加亮顏色的lighten。

# 註解
兩條斜線(//)就可以加入註解。CSS 的話是規定要用/*...*/的註解記號
