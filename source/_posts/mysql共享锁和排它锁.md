---
title: mysql共享锁和排它锁
date: 2021-03-10 14:38:37
tags:
---
# 共享锁和排它锁都是悲观锁的一种

## 共享锁
    共享锁在事务中可以防止其他语句的增删改，可以查询

### 排它锁
    排他锁在事务中可以防止其他共享锁和排它锁的查询