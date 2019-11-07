---
title: 为什么要学习设计模式
date: 2019-11-04 22:30:51
categories:
- 设计模式
- 打卡
tags:
- 设计模式
---

设计模式是特定场景下, 不断重复出现并被采用的解决问题的方式.

学习设计模式, 是为了能够写出更好的代码, 根据场景将关注点分离开来, 写出更加利于维护的代码.


<!-- more -->

## 打卡

打卡1:

今天学习: 设计模式01课, 为什么要学习设计模式;

收获: 学好设计模式, 可以:
1. 提高面试成功率;
2. 写出更好的代码;
3. 提高分析和解决复杂问题的能力;
4. 能够更容易理解优秀的代码设计;
5. 为成为项目管理者等职业道路铺好道路.

## 经历01

最开始工作的时候, 也看过一些书, 比如《Head First 设计模式》.

工作中要使用根据后台数据来给用户生成 Excel 报告, 于是我就想着使用模板方法设计模式, 来创建了一个专门生成报告的抽象类, 定义了生成报表头, 生成报表内容等一系列抽象方法, 后面生成不同报表, 就可以重写定义的抽象方法即可.

后来用来修改报告也很方便, 只需要改动单个类中的方法就可以; 不过抽象的模板可能还是有问题, 又因为使用的类库比较复杂, 改动一个模版也是要花些时间来对应代码中的表头和表内容部分.

另外, 当时的领导也抱怨只是生成个报告, 弄了太多类出来. 这也是设计模式的缺点, 会增加更多的类, 从某一方面来讲也间接提高来代码的复杂度.

## 经历02

后来不经意间又在晚上找到了一个很好的学习设计模式的材料, 里面列举了每种设计模式的意图, 要解决的问题, 解决方案是什么, 等等等等, 是一份很好的参考材料.

[w3s Design](http://w3sdesign.com/index0100.php)

看了这个一遍, 才了解设计深了一步.

以前都只是照猫画虎, 并不理解为什么要做, 每种设计模式要做什么, 或者说是要分离怎么样的变化点.