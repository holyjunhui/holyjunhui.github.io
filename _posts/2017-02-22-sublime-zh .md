---
layout:     post
title:      sublime 侧边栏中文显示有小方块"
subtitle:   "sublime"
date:       2017-02-22
author:     "Junhui"
header-img: "img/bj.jpg"
tags:
    - 前端开发
    - sublime
---
Sublime 显示中文
中文文件名打开全是乱码，内容与装了插件无关，与屏幕dpi有关
在sublime text 3中，打开 Preferences-Settings-user，在括号内加入一行
~~~
{
    "color_scheme": "Packages/User/SublimeLinter/Monokai (SL).tmTheme",
    "dpi_scale": 1.0,##主要是这行起作用
    "font_face": "Consolas",
    "font_size": 14,
    "ignored_packages":
    [
        "Vintage"
    ],
    "line_padding_bottom": 1,
    "line_padding_top": 1,
    "tab_size": 4,
    "translate_tabs_to_spaces": true,
    "word_wrap": "true"
}
~~~

  




