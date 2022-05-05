# SQL RIGHT JOIN 关键字
## SQL RIGHT JOIN 关键字
RIGHT JOIN 关键字从右表（table2）返回所有的行，即使左表（table1）中没有匹配。如果左表中没有匹配，则结果为 NULL。
### SQL RIGHT JOIN 语法
```
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name=table2.column_name;
```
或
```
SELECT column_name(s)
FROM table1
RIGHT OUTER JOIN table2
ON table1.column_name=table2.column_name;
```
**注释**：在某些数据库中，RIGHT JOIN 称为 RIGHT OUTER JOIN。

![image](https://user-images.githubusercontent.com/18340126/163331894-9ce42dbc-7cc9-4088-b3e8-050ee350e972.png)

## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

操作前先在 access_log 表添加一条数据，该数据在 Websites 表没有对应的数据：

```
INSERT INTO `access_log` (`aid`, `site_id`, `count`, `date`) VALUES ('10', '6', '111', '2016-03-09');

下面是选自 "Websites" 表的数据：

+----+--------------+---------------------------+-------+---------+
| id | name         | url                       | alexa | country |
+----+--------------+---------------------------+-------+---------+
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝          | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程      | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博          | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |
| 7  | stackoverflow | http://stackoverflow.com/ |   0 | IND     |
+----+---------------+---------------------------+-------+---------+
```

下面是 "access_log" 网站访问记录表的数据：

```
mysql> SELECT * FROM access_log;
+-----+---------+-------+------------+
| aid | site_id | count | date       |
+-----+---------+-------+------------+
|   1 |       1 |    45 | 2016-05-10 |
|   2 |       3 |   100 | 2016-05-13 |
|   3 |       1 |   230 | 2016-05-14 |
|   4 |       2 |    10 | 2016-05-14 |
|   5 |       5 |   205 | 2016-05-14 |
|   6 |       4 |    13 | 2016-05-15 |
|   7 |       3 |   220 | 2016-05-15 |
|   8 |       5 |   545 | 2016-05-16 |
|   9 |       3 |   201 | 2016-05-17 |
+-----+---------+-------+------------+
9 rows in set (0.00 sec)
```

## SQL RIGHT JOIN 实例
下面的 SQL 语句将返回网站的访问记录。

以下实例中我们把 Websites 作为左表，access_log 作为右表：

> 实例
> SELECT websites.name, access_log.count, access_log.date
> FROM websites
> RIGHT JOIN access_log
> ON access_log.site_id=websites.id
> ORDER BY access_log.count DESC;

执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/163332103-9ee62e50-3c51-4e3e-8230-33d6ade0e5a1.png)

**注释**：RIGHT JOIN 关键字从右表（access_log）返回所有的行，即使左表（Websites）中没有匹配。
