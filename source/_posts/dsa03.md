---
title: 03链表
categories:
  - 数据结构与算法
  - 打卡
tags:
  - 数据结构
  - 算法
date: 2019-11-26 16:20:15
---

## 学习目标

* 常见的链表类型
* 链表的内存结构以及特点
* 数组与链表的区别
* 链表常用操作的写法

<!-- more -->

## 练习

* 单链表反转
* 链表中环的检测
* 两个有序的链表合并
* 删除链表倒数第 n 个结点
* 求链表的中间结点


## 打卡

打卡day03:

今天学习: 数据结构与算法之链表

收获: 理解链表的内存结构以及特性, 针对不同的场景使用不同的数据结构.

### 链表

链表可分为: 单链表, 双向链表, 循环链表, 双向循环链表;

链表也是一种线性表数据结构, 元素与元素之间的内存空间通常不是连续的. 所以链表无法像数组那样通过内存寻址的方式随机访问任意节点.

链表的每个元素, 通常成为节点(Node). 
单链表的每个节点都包含当前元素的值, 和下一个元素节点的引用(后继节点).
双向链表的每个节点都包含当前元素的值, 上一个元素节点的引用(前驱节点), 和下一个元素节点的引用(后继节点).
循环链表的最后一个元素的后继节点引用指向链表的第一个节点.

### 复杂度分析

由于链表无法像内存那样通过内存寻址的方式随机访问任意节点, 只能从第一个节点开始遍历, 所以:
* 单链表访问任意节点的(加权)平均时间复杂度为 O(n);
* 链表添加或删除一个元素的时间复杂度为 O(1);

**实际工作中更常用的是双向链表**, 尽管为占用更多的内存空间, 但是使用起来效率会更高.
当要删除链表中的某个指定元素时, 
* 由于单链表无法访问前驱节点, 只能从第一节点开始遍历, 实际时间复杂度为 O(n);
* 而双向链表可以直接访问前驱节点, 实际时间复杂度为 O(1);

### 数组与链表的区别

数组拥有连续的内存空间, 而链表不在一块连续的内存空间上.

* 从机器缓存的角度, 数组元素的访问可以利用 CPU 缓存, 从而访问效率更高, 而链表则无法利用这一特性;
* 数组每次创建都要申请一块连续的内存空间, 对内存使用条件要求较高; 不支持动态扩容, 每当容量不够的, 需要重新申请一块更大的内存, 还要进行数据复制迁移;
* 链表由于使用不连续的内存空间, 通过引用访问元素, 天生就支持动态扩容, 但是使用中也容易产生内存碎片, 影响机器效率.
* 数组随机访问速度快, 增删元素速度慢; 链表增删元素速度快, 随机访问速度慢.

工作中应针对不同的使用场景使用不同类型数据结构, 增删元素多则使用链表, 随机访问查询多则使用数组.

### 链表代码实践

* 注意引用
* 增删元素时注意操作顺序, 防止指针丢失
* 巧用哨兵机制
* 注意边界条件的检查
* 画图帮助理解
* 多多练习
