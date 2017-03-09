---
layout:     post
title:      "div水平居中"
subtitle:   "css"
date:       2014-09-09
author:     "Junhui"
header-img: "img/img-bg.jpg"
tags:
    - 前端开发
    - css
---

###如何居中一个div
1. 水平居中：给div设置一个宽度，然后添加margin：0 auto；
> div {
>  width:200px;
>  margin:0 auto;
>  }

2. 让绝对定位的div居中；
> div {
>  position:absolute;
>  width:200px;
>  height:200px;
>  margin:auto;
>  top:0;
>  right:0;
>  bottom:0;
>  left:0;
>  background-color:pink;  为了更方便的看效果
>  }

3.水平垂直居中一
>确定容器的宽高， 宽500px 高300px的层，设置层的外边距
>div {
>position:relative;  相对定位或者绝对定位都行
>width:500px;
>height:300px;
>top:50%;
>left:50%;
>margin:-150px,0,0,-250px; 外边距为自身高度的一半
>background-color：pink；为了更方便看效果
>}

4.水平垂直居中二
>利用容器的宽高，利用transform 属性
>div {
>position:absolute; 绝对定位或者相对定位都行
>width:500px;
>height:300px;
>top:50%;
>left:50%;
>transform:translate (-50%,-50%);
>background-color:pink; 为了更方便看效果
>}

5. 水平垂直居中三
>利用flex布局
>实际用的时候注意兼容性
>.container{
>display:flex;
>align-items:center;  垂直居中
>justify-content:center;  水平居中
>}
>.container {
>width:100px;
>height:100px;
>background-color:pink 为了看方便
>}