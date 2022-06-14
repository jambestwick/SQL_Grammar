# SQL EXISTS 运算符
## EXISTS 运算符
EXISTS 运算符用于判断查询子句是否有记录，如果有一条或多条记录存在返回 True，否则返回 False。
### SQL EXISTS 语法
```sql

SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```

## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "Websites" 表的数据：

| id  | name         | url                       | alexa | country |
|:---:|:------------:|:-------------------------:|:-----:|:-------:|
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝       | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程 | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博       | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |

下面是 "access_log" 网站访问记录表的数据：

```sql
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

## SQL EXISTS 实例
现在我们想要查找总访问量(count 字段)大于 200 的网站是否存在。

我们使用下面的 SQL 语句：

实例

```sql
SELECT Websites.name, Websites.url 
FROM Websites 
WHERE EXISTS (SELECT count FROM access_log WHERE Websites.id = access_log.site_id AND count > 200);
```
执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/173586276-8940f46f-c3e1-45e5-9756-0a89717439db.png)

EXISTS 可以与 NOT 一同使用，查找出不符合查询语句的记录：

实例
```sql
SELECT Websites.name, Websites.url 
FROM Websites 
WHERE NOT EXISTS (SELECT count FROM access_log WHERE Websites.id = access_log.site_id AND count > 200);
```
执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/173586508-1c4987a1-2ae1-4d59-bc47-22efdd625041.png)
