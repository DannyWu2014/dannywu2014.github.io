---
title: 事务隔离
categories:
  - MySQL
tags:
  - MySQL
  - 事务
date: 2019-11-27 16:23:17
---

## 学习目标

MySQL03

* 四种事务隔离级别以及应用场景
* 事务的实现机制和 MVCC
* 长事务的风险

<!-- more -->

## 事务隔离级别

* 读未提交(read uncommitted)
  事务 A 可以读到事务 B 未提交的内容
* 读提交(read committed)
  事务 A 只能读到事务 B 提交后的内容
  Oracle 默认隔离级别
* 可重复读(repeatable read)
  事务 A 只能读到事务 A 开启时事务 B 所提交的内容
  MySQL 默认隔离级别
  比如可以用于数据校对
* 串行化(serializable)
  加锁, 每次保证只有一个事务能够执行.

隔离级别越高, 数据库性能越差.

## 事务实现机制

MVCC, 多版本并发控制, 同一条记录在系统中可以存在多个版本.

MySQL 中读提交和可重复读两种级别下是通过创建**视图**来实现事务隔离的.
- 读提交时, 视图在每条 SQL 开始执行时创建的;
- 可重复读时, 视图是在每个事务开启时创建的, 整个事务期间都会使用这个视图;

在 MySQL 中, 每条记录在被更新时, 同时也会创建一个回滚操作. 这样记录中的最新值就可以通过该回滚操作, 得到原来状态下的值.

这样, 在可重复读隔离级别下, 事务 A 更新了记录 R1, 会生成一个回滚操作记录 RB1, 这时事务 B 进来会生成一个视图 read_view1, 事务 B 可以在 read_view1 中根据 RB1 的回滚操作来访问记录 R1 在被事务 A 更新前的记录值了.

只有当系统判断, 不会再有事务会用到这些回滚日志的时候, 这些日志才会被删除.

## 长事务风险

长事务, 也就意味着其中的回滚日志都需要保留, 占用系统存储空间.
同时, 长事务也会占用锁资源, 导致数据库性能下降.


