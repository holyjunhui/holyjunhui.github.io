
---
layout:     post
title:      "CSS选择器笔记"
subtitle:   "CSS"
date:       2016-10-04
author:     "Junhui"
header-img: "img/css.png"
tags:
    - 前端开发
    - css
---
###CSS选择器笔记

这几天学习中发现，有些选择器容易搞混，在使用中会搞得自己晕头转向的，所以根据现有水平，总结一下css选择器，其中包括css3选择器。


==========================================================================

####一. 基本选择器

| 序号| 选择器 | 含义|
|:----|:-----|:----------|
|1.|E,F|多元素选择器，同时匹配所有E元素或者F元素，E和F之间用逗号隔开
|2.|E F|后代选择器，匹配所有属于E元素后代的F元素，E和F之间用空格隔开|
|3.|E>F|子代选择器，匹配所有E元素的子元素F
|4.|E+F|相邻元素，匹配所有紧邻E元素之后的同级元素F

备注：
1.子代选择器，子元素选择器（Child selectors）只能选择作为某元素子元素的元素。简单的说就是有直接的父元素。
>例如： 这个规则会把第一个 h1 下面的两个 strong 元素变为红色，但是第二个 h1 中的 strong 不受影响：

>`<h1>This is <strong>very</strong> <strong>very</strong> important.</h1>`
>`<h1>This is <em>really <strong>very</strong></em> important.</h1>`

2.后代选择器，后代选择器（descendant selector）又称为包含选择器。
后代选择器可以选择作为某元素后代的元素。
>上面这个规则会把作为 h1 元素后代的 em 元素的文本变为 红色。其他 em 文本（如段落或块引用中的 em）则不会被这个规则选中：
`<h1>This is a <em>important</em> heading</h1>`
`<p>This is a <em>important</em> paragraph.</p>`

例如，如果写作 ul em，这个语法就会选择从 ul 元素继承的所有 em 元素，而不论 em 的嵌套层次多深。
因此，ul em 将会选择以下标记中的所有 em 元素：
>`<ul>
  <li>List item 1
    <ol>
      <li>List item 1-1</li>
      <li>List item 1-2</li>
      <li>List item 1-3
        <ol>
          <li>List item 1-3-1</li>
          <li>List item <em>1-3-2</em></li>
          <li>List item 1-3-3</li>
        </ol>
      </li>
      <li>List item 1-4</li>
    </ol>
  </li>
  <li>List item 2</li>
  <li>List item 3</li>
</ul>`

3.相邻兄弟选择器，相邻兄弟选择器（Adjacent sibling selector）可选择紧接在另一元素后的元素，且二者有相同父元素。

#####选择相邻兄弟
如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。
例如，如果要增加紧接在 h1 元素后出现的段落的上边距，可以这样写：
h1 + p {margin-top:50px;}
这个选择器读作：“选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素”。
>`<div>
  <ul>
    <li class="active">List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ul>
  <ol>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ol>
</div>`
在上面的片段中，div 元素中包含两个列表：一个无序列表，一个有序列表，每个列表都包含三个列表项。这两个列表是相邻兄弟，列表项本身也是相邻兄弟。不过，第一个列表中的列表项与第二个列表中的列表项不是相邻兄弟，因为这两组列表项不属于同一父元素（最多只能算堂兄弟）。
请记住，用一个结合符只能选择两个相邻兄弟中的第二个元素。请看下面的选择器：
li + li {font-weight:bold;}
上面这个选择器只会把列表中的第二个和第三个列表项变为粗体。第一个列表项不受影响。
因为上面的li+li其中第二li是第一li的相邻元素，第三个又是第二个相邻元素，因此第三个也被选择，依此类推著作权归作者所有。
商业转载请联系作者获得授权,非商业转载请注明出处。
原文: https://www.w3cplus.com/css3/basic-selectors © w3cplus.com
相对于是指针对一个元素，即li+li 是给后面的li添加样式.
如果是这行代码`.active + li {background: green;color: yellow; border: 1px solid #ccc;}
这句代码很明显选择了li.active后面相邻的li元素，注意了和li.active后面相邻的元素仅有一个，即第二个li变色。

####3.CSS2.1 属性选择器
|序号|选择器|含义
|:---|:---|:---|
|1.|E[att]|匹配所有具有att属性的E元素，不考虑它的值。（注意：E在此处可以省略，比如"[cheacked]"。以下同。）
|2.|E[att=val]|匹配所有att属性等于"val"的E元素
|3.|E[att~=val]|匹配所有att属性具有多个空格分隔的值、其中一个值等于"val"的E元素
|4.|E[att\|=val]|匹配所有att属性具有多个连字号分隔（hyphen-separated）的值、其中一个值以"val"开头的E元素，主要用于lang属性，比如"en"、"en-us"、"en-gb"等等

实例：
>p[title] { color:#f00; }
div[class=error] { color:#f00; }
td[headers~=col1] { color:#f00; }
p[lang|=en] { color:#f00; }
blockquote[class=quote][cite] { color:#f00; }
####4. CSS2.1中的伪类
|序号|选择器|含义
|:-----|:----|:---
|1.|E:first-child|匹配父元素的第一个子元素
|2.|E:link|匹配所有未被点击的链接
|3.|E:visited|匹配所有已被点击的链接
|4.|E:active|匹配鼠标已经其上按下、还没有释放的E元素
|5.|E:hover|匹配鼠标悬停其上的E元素
|6.|E:focus|匹配获得当前焦点的E元素
|7.|E:lang(c)|匹配lang属性等于c的E元素
实例：
>p:first-child { font-style:italic; }
input[type=text]:focus { color:#000; background:#ffe; }
input[type=text]:focus:hover { background:#fff; }
q:lang(sv) { quotes: "\201D" "\201D" "\2019" "\2019"; }

####5.CSS2.1中的伪元素
|序号|选择器|含义
|:---|:---|:---
|1.|E:first-line|匹配E元素的第一行
|2.|E:first-letter|匹配E元素的第一个字母
|3.|E:before|在E元素之前插入生成的内容
|4.|E:after|在E元素之后插入生成的内容

实例：
>p:first-line { font-weight:bold; color;#600; }
.preamble:first-letter { font-size:1.5em; font-weight:bold; }
.cbb:before { content:""; display:block; height:17px; width:18px; background:url(top.png) no-repeat 0 0; margin:0 0 0 -18px; }
a:link:after { content: " (" attr(href) ") "; }
