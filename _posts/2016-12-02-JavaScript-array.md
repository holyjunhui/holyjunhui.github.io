---
layout:     post
title:      "JavaScript中数组操作方法"
subtitle:   "JavaScript"
date:       2016-10-02
author:     "Junhui"
header-img: "img/post-bg-version.jpg"
tags:
    - 前端开发
    - javasript
---

### JavaScript数组操作方法

#### 一、数组的常用方法
##### 1、数组元素的添加
> arrayObj. push([item1 [item2 [. . . [itemN ]]]]);// 将一个或多个新元素添加到数组结尾，并返回数组新长度

> arrayObj.unshift([item1 [item2 [. . . [itemN ]]]]);// 将一个或多个新元素添加到数组开始，数组中的元素自动后移，返回数组新长度

> arrayObj.splice(insertPos,0,[item1[, item2[, . . . [,itemN]]]]);//将一个或多个新元素插入到数组的指定位置，插入位置的元素自动后移，返回""。
##### 2、数组的删除
> arrayObj.pop(); //移除最后一个元素并返回该元素值,  <b>这个会改变原数组，返回移除的元素值</b>
> 
> arrayObj.shift(); //移除最前一个元素并返回该元素值，数组中元素自动前移 ，<b>这个会改变原数组，返回移除的元素值</b>
> 
> arrayObj.splice(deletePos,deleteCount); //删除从指定位置deletePos开始的指定数量deleteCount的元素，数组形式返回所移除的元素
#####3、数组的截取与合并
>arrayObj.slice(start, [end]); //以数组的形式返回数组的一部分，注意不包括 end 对应的元素，如果省略 end 将复制 start 之后的所有元素 **可以看成是左闭右开区间[   );**
>
> arrayObj.concat([item1[, item2[, . . . [,itemN]]]]); //将多个数组（也可以是字符串，或者是数组和字符串的混合）连接为一个数组，返回连接好的新的数组 **concat 是混合，如果这些参数中的任何一个自身是数组，则连接的是数组的元素，而不是数组本身，如果是 [5,6].concat.([1,2,3])  // 组合为[5,6,1,2,3] 如果是 [1,2,3].concat([7,[8,9]]) //组合为[1,2,3,7,[8,9]]**

#####4、数组的排序
>arrayObj.reverse(); //反转元素（最前的排到最后、最后的排到最前），返回数组地址 **这是数组的逆序排列。既是将数组中的元素颠倒顺序，返回逆序的数组，采取的是替换，它不通过重新排列的元素创建新数组，而是在原先的数组中重新排列他们**  var a=[1,2,3];  a.reverse().join()  // "3,2,1" 并且现在的a是[3,2,1]
> array.sort() 方法将数组中的元素排序并返回排序后的数组，当不带参数调用sort() 时，数组元素以字母表顺序排序，（如有必要将临时转化为字符串进行比较）