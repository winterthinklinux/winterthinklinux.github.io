---
layout: post
title:  mysql join
tags: mysql
category: mysql
date: 2015-04-11 23:22:26
---

### 如何使用 MySQL 的 JOIN 在两个或多个表中查询数据。
- SELECT, UPDATE 和 DELETE 语句中使用 Mysql 的 JOIN 来联合多表查询。
- INNER JOIN（内连接,或等值连接）：获取两个表中字段匹配关系的记录。
- LEFT JOIN（左连接）：获取左表所有记录，即使右表没有对应匹配的记录。
- RIGHT JOIN（右连接）： 与 LEFT JOIN 相反，用于获取右表所有记录，即使左表没有对应匹配的记录


![]( https://raw.githubusercontent.com/winterthinklinux/mdpics/master/images/mysql/img_innerjoin.gif)
![]( https://raw.githubusercontent.com/winterthinklinux/mdpics/master/images/mysql/img_leftjoin.gif)
![]( https://raw.githubusercontent.com/winterthinklinux/mdpics/master/images/mysql/img_rightjoin.gif)


![]( https://raw.githubusercontent.com/winterthinklinux/mdpics/master/images/mysql/runoob_tbl.png)
![]( https://raw.githubusercontent.com/winterthinklinux/mdpics/master/images/mysql/tcount_tbl.png)
```bash
SELECT a.runoob_id, a.runoob_author, b.runoob_count FROM runoob_tbl a INNER JOIN tcount_tbl b ON a.runoob_author = b.runoob_author;
```
等价于
```bash
SELECT a.runoob_id, a.runoob_author, b.runoob_count FROM runoob_tbl a, tcount_tbl b WHERE a.runoob_author = b.runoob_author;
```
![]( https://raw.githubusercontent.com/winterthinklinux/mdpics/master/images/mysql/inner_join..png)


外连接：

左外连接：
```bash
SELECT a.runoob_id, a.runoob_author, b.runoob_count FROM runoob_tbl a LEFT JOIN tcount_tbl b ON a.runoob_author = b.runoob_author;
```
右外连接：
```bash
SELECT b.runoob_id, b.runoob_author, a.runoob_count FROM tcount_tbl a RIGHT JOIN runoob_tbl b ON a.runoob_author = b.runoob_author;
```
