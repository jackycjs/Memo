# Css

### 1. 语法

- #### 定义一个icon-font

``` scss
@font-face {

  font-family: 字体名称;
  src: 服务器上字体文件的路径;
}

@font-face {
  font-family: "iconfont";
  src: url('iconfont.eot'); /* IE9*/
  src: url('iconfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
       url('iconfont.woff') format('woff'), /* chrome、firefox */
       url('iconfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
       url('iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */
}

.iconfont {
  font-family:"iconfont" !important;
  font-size:16px;
  font-style:normal;
  -webkit-font-smoothing: antialiased;
  -webkit-text-stroke-width: 0.2px;
  -moz-osx-font-smoothing: grayscale;
}
```


- #### 定义一个key-frames ( 关键帧 )

``` scss
@key-frames changecolor {

  from { background:red; }

  to { background:green; }
}

animation-name: changecolor /*( 动画的名称 );*/

                /*-webkit- -moz- 前缀*/

animation-duration: 1/*动画播放时间;*/

animation-timing-function: 1/*动画播放方式;*/

animation-delay: 1/*等待时间;*/

animation-iteration-count: 1/*播放次数;*/

animation-direction: alternate /*( 动画播放方向 ) ;*/

animation-play-state: running, paused /*( 播放/暂停 );*/

animation-fill-mode: 1/*设置时间外属性;*/
```

- #### flex兼容写法

``` scss
.flex {
  display: -webkit-box;  /*老版本语法: Safari, iOS, Android browser, older WebKit browsers. */
  display: -moz-box;  /*老版本语法: Firefox (buggy) */
  display: -ms-flexbox;  /*混合版本语法: IE 10 */
  display: -webkit-flex;  /*新版本语法: Chrome 21+ */
  display: flex;  /*新版本语法: Opera 12.1, Firefox 22+*/

  flex-grow: 1;
  -webkit-box-flex: 1.0;
  -moz-flex-grow: 1;
  -webkit-flex-grow: 1;
}
```

---
&nbsp;

### 2. Css样式收集
- #### Animate.css 网站标题 渐变色字体动画效果

``` scss
.site__title {
  color: #f35626;
  background-image: -webkit-linear-gradient(92deg,#f35626,#feab3a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-animation: hue 60s infinite linear;
}

@-webkit-keyframes hue {
  from {
    -webkit-filter: hue-rotate(0deg);
  }
  to {
    -webkit-filter: hue-rotate(-360deg);
  }
}
```

- #### reset.css
``` scss
/*一.最简化的CSS Reset(重设) :*/

* {
      padding: 0;
      margin: 0;
}
　　/*这是最普遍最简单的CSS重设，将所有元素的padding和margin值都设为0，可以避免一些浏览器在理解这两个属性默认值上的”分歧”。*/

* {
      padding: 0;
      margin: 0;
      border: 0;
}
　　/*这是在上一个重设的基础上添加了对border属性的重设，初始值为0的确能避免一些问题。*/

* {
      outline: 0;
      padding: 0;
      margin: 0;
      border: 0;
}
　　/*在前两个的基础上添加了outline属性的重设，防止一些冲突。*/


/*二.浓缩实用型CSS Reset(重设):*/

* {
      vertical-align: baseline;
      font-weight: inherit; 
      font-family: inherit; 
      font-style: inherit;
      font-size: 100%;
      outline: 0;
      padding: 0;
      margin: 0;
      border: 0;
}
　　/*该CSS重设方法出自Perishable Press，这是他常用的方法。*/


/*三.Poor Man 的CSS Reset:*/

html, body { 
      padding: 0; 
      margin: 0; 
}
html {
      font-size:1em;
} 
body {
      font-size:100%;
} 
a img, :link img, :visited img {
      border:0px;
}
　　/*这个重设方法将html和body下元素的padding和margin都设为0，并分别为html标签和body标签下的所有元素设置了初始的字体大小，最重要的是把有链接的图片的默认边框去掉了。*/


/*四.Siolon’s Global Reset*/

* { 
    vertical-align: baseline;
    font-family: inherit;
    font-style: inherit;
    font-size: 100%;
    border: none;
    padding: 0;
    margin: 0; 
}
body {
    padding: 5px;
} 
h1, h2, h3, h4, h5, h6, p, pre, blockquote, form, ul, ol, dl {
    margin: 20px 0;
}
li, dd, blockquote { 
    margin-left: 40px;
} 
table { 
    border-collapse: collapse; 
    border-spacing: 0; 
}


/*五.Shaun Inman’s Global Reset*/

body, div, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, pre, form, fieldset, input, p, blockquote, table, th, td, embed, object {
    padding: 0;
    margin: 0; 
}
table {
    border-collapse: collapse;
    border-spacing: 0;
}
    fieldset, img, abbr {
    border: 0;
}
address, caption, cite, code, dfn, em, 
h1, h2, h3, h4, h5, h6, strong, th, var {
    font-weight: normal;
    font-style: normal;
}
ul {
    list-style: none;
}
caption, th {
    text-align: left;
}
h1, h2, h3, h4, h5, h6 {
    font-size: 1.0em;
}
q:before, q:after {
    content: ”;
}
a, ins {
    text-decoration: none;
}


/*六.Yahoo(YUI) CSS Reset:*/

body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre, 
form,fieldset,input,textarea,p,blockquote,th,td { 
    padding: 0; 
    margin: 0; 
} 
table { 
    border-collapse: collapse; 
    border-spacing: 0; 
} 
fieldset,img { 
    border: 0; 
} 
address,caption,cite,code,dfn,em,strong,th,var { 
    font-weight: normal; 
    font-style: normal; 
} 
ol,ul { 
    list-style: none; 
} 
caption,th { 
    text-align: left; 
} 
h1,h2,h3,h4,h5,h6 { 
    font-weight: normal; 
    font-size: 100%; 
} 
q:before,q:after { 
    content:”; 
} 
abbr,acronym { 
    border: 0; 
}


/*七.Eric Meyer’s CSS Reset*/

html, body, div, span, applet, object, iframe, table, caption, 
tbody, tfoot, thead, tr, th, td, del, dfn, em, font, img, ins, 
kbd, q, s, samp, small, strike, strong, sub, sup, tt, var, 
h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, abbr, 
acronym, address, big, cite, code, dl, dt, dd, ol, ul, li, 
fieldset, form, label, legend { 
    vertical-align: baseline; 
    font-family: inherit; 
    font-weight: inherit; 
    font-style: inherit; 
    font-size: 100%; 
    outline: 0; 
    padding: 0; 
    margin: 0; 
    border: 0; 
} 
:focus { 
    outline: 0; 
} 
body { 
    background: white; 
    line-height: 1; 
    color: black; 
} 
ol, ul { 
    list-style: none; 
} 
table { 
    border-collapse: separate; 
    border-spacing: 0; 
} 
caption, th, td { 
    font-weight: normal; 
    text-align: left; 
} 
blockquote:before, blockquote:after, q:before, q:after { 
    content: “”; 
} 
blockquote, q { 
    quotes: “” “”; 
}


/* http://meyerweb.com/eric/tools/css/reset/ 
  v2.0 | 20110126
  License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
}
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
    display: block;
}
body {
    line-height: 1;
}
ol, ul {
    list-style: none;
}
blockquote, q {
    quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
    content: '';
    content: none;
}
table {
    border-collapse: collapse;
    border-spacing: 0;
}


/*八.Condensed Meyer Reset:*/

html, body, div, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, 
pre, form, fieldset, input, textarea, p, blockquote, th, td { 
    padding: 0;
    margin: 0;
}
fieldset, img { 
    border: 0;
}
table {
    border-collapse: collapse;
    border-spacing: 0;
}
ol, ul {
    list-style: none;
}
address, caption, cite, code, dfn, em, strong, th, var {
    font-weight: normal;
    font-style: normal;
}
caption, th {
    text-align: left;
}
h1, h2, h3, h4, h5, h6 {
    font-weight: normal;
    font-size: 100%;
}
q:before, q:after {
    content: ”;
}
abbr, acronym { 
    border: 0;
}


/*九.Ateneu Popular CSS Reset*/

html, body, div, span, applet, object, iframe, h1, h2, h3, 
h4, h5, h6, p, blockquote, pre, a, abbr, acronym, 
address, big, cite, code, del, dfn, em, font, img, ins, 
kbd, q, s, samp, small, strike, strong, sub, sup, tt, 
var, dl, dt, dd, ol, ul, li, fieldset, form, label, legend, 
table, caption, tbody, tfoot, thead, tr, th, td { 
    margin: 0; 
    padding: 0; 
    border: 0; 
    outline: 0; 
    font-weight: inherit; 
    font-style: inherit; 
    font-size: 100%; 
    font-family: inherit; 
    vertical-align: baseline; 
} 
:focus {
    outline: 0;
} 
a, a:link, a:visited, a:hover, a:active{
    text-decoration:none
} 
table {
    border-collapse: separate;
    border-spacing: 0;
} 
th, td {
    text-align: left;
    font-weight: normal;
} 
img, iframe {
    border: none;
    text-decoration:none;
} 
ol, ul {
    list-style: none;
} 
input, textarea, select, button {
    font-size: 100%;
    font-family: inherit;
} 
select {
    margin: inherit;
} 
hr {
    margin: 0;
    padding: 0;
    border: 0;
    color: #000;
    background-color: #000;
    height: 1px
}


/*十.Chris Poteet’s Reset CSS*/

* { 
    vertical-align: baseline; 
    font-family: inherit; 
    font-style: inherit; 
    font-size: 100%; 
    border: none; 
    padding: 0; 
    margin: 0; 
} 
body { 
    padding: 5px; 
} 
h1, h2, h3, h4, h5, h6, p, pre, blockquote, form, ul, ol, dl { 
    margin: 20px 0; 
} 
li, dd, blockquote { 
    margin-left: 40px; 
} 
table { 
    border-collapse: collapse; 
    border-spacing: 0; 
}


/*十一.Tantek Celik Reset CSS*/

:link,:visited { text-decoration:none } 
ul,ol { list-style:none } 
h1,h2,h3,h4,h5,h6,pre,code { font-size:1em; } 
ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,body,html,p,blockquote,fieldset,input 
{ margin:0; padding:0 } 
a img,:link img,:visited img { border:none } 
address { font-style:normal }


/*十二.Christian Montoya Reset CSS*/

html, body, form, fieldset { 
    margin: 0; 
    padding: 0; 
    font: 100%/120% Verdana, Arial, Helvetica, sans-serif; 
} 
h1, h2, h3, h4, h5, h6, p, pre, 
blockquote, ul, ol, dl, address { 
    margin: 1em 0; 
    padding: 0; 
} 
li, dd, blockquote { 
    margin-left: 1em; 
} 
form label { 
    cursor: pointer; 
} 
fieldset { 
    border: none; 
} 
input, select, textarea { 
    font-size: 100%; 
    font-family: inherit; 
}


/*十三.Rudeworks Reset CSS*/

* { 
    margin: 0; 
    padding: 0; 
    border: none; 
} 
html { 
    font: 62.5% “Lucida Grande”, Lucida, Verdana, sans-serif; 
    text-shadow: #000 0px 0px 0px; 
} 
ul { 
    list-style: none; 
    list-style-type: none; 
} 
h1, h2, h3, h4, h5, h6, p, pre, 
blockquote, ul, ol, dl, address { 
    font-weight: normal; 
    margin: 0 0 1em 0; 
} 
cite, em, dfn { 
    font-style: italic; 
} 
sup { 
    position: relative; 
    bottom: 0.3em; 
    vertical-align: baseline; 
} 
sub { 
    position: relative; 
    bottom: -0.2em; 
    vertical-align: baseline; 
} 
li, dd, blockquote { 
    margin-left: 1em; 
} 
code, kbd, samp, pre, tt, var, input[type=’text’], textarea { 
    font-size: 100%; 
    font-family: monaco, “Lucida Console”, courier, mono-space; 
} 
del { 
    text-decoration: line-through; 
} 
ins, dfn { 
    border-bottom: 1px solid #ccc; 
} 
small, sup, sub { 
    font-size: 85%; 
} 
abbr, acronym { 
    text-transform: uppercase; 
    font-size: 85%; 
    letter-spacing: .1em; 
    border-bottom-style: dotted; 
    border-bottom-width: 1px; 
} 
a abbr, a acronym { 
    border: none; 
} 
sup { 
    vertical-align: super; 
} 
sub { 
    vertical-align: sub; 
} 
h1 { 
    font-size: 2em; 
} 
h2 { 
    font-size: 1.8em; 
} 
h3 { 
    font-size: 1.6em; 
} 
h4 { 
    font-size: 1.4em; 
} 
h5 { 
    font-size: 1.2em; 
} 
h6 { 
    font-size: 1em; 
} 
a, a:link, a:visited, a:hover, a:active { 
    outline: 0; 
    text-decoration: none; 
} 
a img { 
    border: none; 
    text-decoration: none; 
} 
img { 
    border: none; 
    text-decoration: none; 
} 
label, button { 
    cursor: pointer; 
} 
input:focus, select:focus, textarea:focus { 
    background-color: #FFF; 
} 
fieldset { 
    border: none; 
} 
.clear { 
    clear: both; 
} 
.float-left { 
    float: left; 
} 
.float-right { 
    float: right; 
} 
body { 
    text-align: center; 
} 
#wrapper { 
    margin: 0 auto; 
    text-align: left; 
}


/*十四. Anieto2K Reset CSS*/

html, body, div, span, applet, object, iframe, 
h1, h2, h3, h4, h5, h6, p, 
blockquote, pre, a, abbr, acronym, address, big, 
cite, code, del, dfn, em, font, img, 
ins, kbd, q, s, samp, small, strike, 
strong, sub, sup, tt, var, dl, dt, dd, ol, ul, li, 
fieldset, form, label, legend, 
table, caption, tbody, tfoot, thead, tr, th, td, 
center, u, b, i { 
    margin: 0; 
    padding: 0; 
    border: 0; 
    outline: 0; 
    font-weight: normal; 
    font-style: normal; 
    font-size: 100%; 
    font-family: inherit; 
    vertical-align: baseline 
} 
body { 
    line-height: 1 
} 
:focus { 
    outline: 0 
} 
ol, ul { 
    list-style: none 
} 
table { 
    border-collapse: collapse; 
    border-spacing: 0 
} 
blockquote:before, blockquote:after, q:before, q:after { 
    content: “” 
} 
blockquote, q { 
    quotes: “” “” 
} 
input, textarea { 
    margin: 0; 
    padding: 0 
} 
hr { 
    margin: 0; 
    padding: 0; 
    border: 0; 
    color: #000; 
    background-color: #000; 
    height: 1px 
}


/*十五.CSSLab CSS Reset*/

html, body, div, span, applet, object, iframe, h1, h2, h3, 
h4, h5, h6, p, blockquote, pre, a, abbr, acronym, address, 
big, cite, code, del, dfn, em, font, img, ins, kbd, q, s, samp, 
small, strike, strong, sub, sup, tt, var, dl, dt, dd, ol, ul, li, 
fieldset, form, label, legend, table, caption, tbody, tfoot, 
thead, tr, th, td { 
    margin: 0; 
    padding: 0; 
    border: 0; 
    outline: 0; 
    font-weight: inherit; 
    font-style: inherit; 
    font-size: 100%; 
    font-family: inherit; 
    vertical-align: baseline; 
} 
:focus { 
    outline: 0; 
} 
table { 
    border-collapse: separate; 
    border-spacing: 0; 
} 
caption, th, td { 
    text-align: left; 
    font-weight: normal; 
} 
a img, iframe { 
    border: none; 
} 
ol, ul { 
    list-style: none; 
} 
input, textarea, select, button { 
    font-size: 100%; 
    font-family: inherit; 
} 
select { 
    margin: inherit; 
} 

ol { margin-left:2em; } 
.clearfix:after { 
    content: '.'; 
    display: block; 
    height: 0; 
    clear: both; 
    visibility: hidden; 
} 
.clearfix {display: inline-block;} 
* html .clearfix {height: 1%;} 
.clearfix {display: block;}



/*  
    作者：人人网FED
    链接：https://juejin.im/post/599ececb5188252423583c27
    来源：掘金
    著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
*/
/* IE浏览器对输入控件有自己的font-family，需要统一 */
input,
textarea,
button{
    font-family: inherit;
}

/* Chrome浏览器会在输入控制聚集的时候添加一个蓝色的outline*/
input:focus,
textarea:focus,
select:focus{
    outline: none;
}

/* 去掉textarea的可拉大小功能*/
textarea{
    resize: none;
}

/* IOS Safari在横屏的时候会放大字体，第二个属性让滑动更流畅 */
html{
    -webkit-text-size-adjust: 100%;
    -webkit-overflow-scrolling : touch;
}

/* 统一标签的margin值和p标签的line-height*/
body, p, h1, h2, ul, ol, figure, li{
    padding: 0;
    margin: 0;
}

h1, h2, p{
    line-height: 150%;
}

/* 去掉select的默认样式 */
select{
    -webkit-appearance: none;
}
/* 如果有输入内容IE会给输入框右边加一个大大的X */
input::-ms-clear{
    display: none;
    width: 0;
    height: 0;
}

/* 去掉number输入框右边点击上下的小三角 */
input::-webkit-inner-spin-button{
    -webkit-appearance: none;
}

input::-webki-outer-spin-button{
    -webki-appearance: none;
}
```


- #### webkit滚动条样式

``` scss
::-webkit-scrollbar {
  width: 7px;
  background-color: #f0f0f0;
}
::-webkit-scrollbar-button:start:decrement, ::-webkit-scrollbar-button:end:increment{
  width:0;height:0; 
}   
::-webkit-scrollbar-thumb{
  background:#d0d0d0;
}  
::-webkit-scrollbar-thumb:hover{
  background:#aaaaab;
}
```


- #### Kendo UI 的button 样式
``` scss
.k-button {
  display: inline-block;
  margin: 0;
  padding: 10px 14px;
  font-family: inherit;
  line-height: 1.72em;
  text-align: center;
  cursor: pointer;
  text-decoration: none;

  font-size: 100%;
  font-family: inherit;
  border-style: solid;
  border-width: 1px;
  -webkit-appearance: none;

  color: #444;
  border-color: #fafafa;
  background-color: #fafafa;


  -webkit-box-shadow: 0 2px 6px rgba(0,0,0,0.2),0 2px 3px rgba(0,0,0,0.05);
  box-shadow: 0 2px 6px rgba(0,0,0,0.2),0 2px 3px rgba(0,0,0,0.05);

  border-radius: 2px;
}

.k-primary {
  color: #fff;
  border-color: #3f51b5;
  background-image: none;
  background-position: 50% 50%;
  background-color: #3f51b5;
  -webkit-box-shadow: none;
  box-shadow: none;

  &:hover {
    color: #fff;
    border-color: #5c6bc0;
    background-color: #5c6bc0;
  };
}
```