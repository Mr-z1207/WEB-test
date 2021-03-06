# 笔记

[TOC]

## 语义化

1. 用正确的标签做正确的事情,让页面的内容结构化，便于对浏览器、搜索引擎解析
2. 搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重,利于 SEO
3. 便于阅读维护理解
4. html不是用来显示样式的,默认样式是在没有CCS情况下也以一种文档格式显示，并且是容易阅读的

## 常用字符实体

|显示结果|描述|实体名称|实体编号|
|:---:|:---:|:---:|:---:|
|sped|空格|`&nbsp;`|`&#160;`|
|<|小于号|`&lt;`|`&#60;`|
|>|大于号|`&gt;`|`&#62;`|
|&|和号|`&amp;`|`&#38;`|
|"|引号|`&quot;`|`&#34;`|
|'|撇号 |`&apos;` (IE不支持)|`&#39;`|
|￠|分（cent）|`&cent;`|`&#162;`|
|£|镑（pound）|`&pound;`|`&#163;`|
|¥|元（yen）|`&yen;`|`&#165;`|
|€|欧元（euro）|`&euro;`|`&#8364;`|
|§|小节|`&sect;`|`&#167;`|
|©|版权（copyright）|`&copy;`|`&#169;`|
|®|注册商标|`&reg;`|`&#174;`|
|™|商标|`&trade;`|`&#8482;`|
|×|乘号|`&times;`|`&#215;`|
|÷|除号|`&divide;`|`&#247;`|

## CSS选择器优先级

ID选择器 &gt; 类选择器 &gt; 标签选择器 &gt; 通用选择 器& gt;继承间接选中 &gt; 浏览器默认的样式

## BFC

BFC(Block Fromatting Context)块级格式上下文,BFC是一个独立的布局环境,其中的元素布局是不受外界的影响

如何触发:

- float的值不是none(可以是left或者right)
- position的值不是static或者relative.(可以是absolute或fixed)
- display的值是inline-block、table-cell、flex、table-caption或者inline-flex
- overflow的值不是visible（可以是hidden、scroll、auto）

## 显示模式

### 1.HTML中标签的分类

- #### 容器级

能嵌套其它所有标签的标签

常见的有:
`div` `header` `nav` `section` `article` `footer` `h` `ul` `ol` `dl` `li` `dt` `dd`

- #### 文本级

只能嵌套文字/图片/视频/音频/超链接的标签

常见的有:
`p` `span` `a` `b` `u` `i` `s` `stong` `em` `ins` `del`

---
> 注意: `<a>`标签 可以嵌套其他块元素
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<p>`标签 不可以嵌套其他块元素

### 2.CSS中标签的分类

- #### 常见的块状元素

`p` `div` `header` `nav` `section` `article` `footer` `h` `ul` `ol` `dl` `li` `dt` `dd`

- #### 常见的行内元素

`span` `a` `b` `u` `i` `s` `stong` `em` `ins` `del`

- #### 常见的行内块状元素

`img` `input` `textarea`

- #### css显示模式特点

|特征|块状|行内|行内块|
|:---:|:---:|:---:|:---:|
|是否独占一行|是|否|否|
|是否可以设置宽|是|否|是|
|是否可以设置高|是|否|是|
|默认宽|父元素的宽|内容的宽|内容的宽|
|默认高|内容的高|内容的高|内容的高|
|是否可以设置水平外边距|是|是|是|
|是否可以设置垂直外边距|是|否|是|
|是否可以设置水平内边距|是|是|是|
|是否可以设置垂直内边距|是|可以设置但不占空间|是|
|是否可以设置边框|是|是|是|

### 3.显示模式的转换

`display:模式`

取值有：

- `block` 块级
- `inline` 行内
- `inline-block` 行内块级

## 清除浮动

> 详细见 ./002_css_base/010_清除浮动.html

```css
.clearfix::after{
    content: '';
    clear: both;
    display: block;
    height: 0px;
    visibility: hidden;
}
/* IE8以上才支持after IE6、IE7用zoom:1 */
.clearfix{
    zoom:1;
}
```

## CSS3兼容前缀

- `-webkit-`　chrome、safari
- `-moz-`　firefox
- `-ms-`   IE
- `-o-`   opera

## 杂记

css3为了区分伪类和伪元素，伪元素采用双冒号写法。

- 常见伪类: `:hover` `:link` `:active` `:target` `:not()` `:focus`

- 常见伪元素 `::first-letter` `::first-line` `::before` `::after` `::selection`
