# SQL 别名
通过使用 SQL，可以为表名称或列名称指定别名。
## SQL 别名
通过使用 SQL，可以为表名称或列名称指定别名。

基本上，创建别名是为了让列名称的可读性更强。
### 列的 SQL 别名语法
```
SELECT column_name AS alias_name
FROM table_name;
```
### 表的 SQL 别名语法

```
SELECT column_name(s)
FROM table_name AS alias_name;
```

## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "Websites" 表的数据：

```sql
mysql> SELECT * FROM Websites;
+----+---------------+---------------------------+-------+---------+
| id | name          | url                       | alexa | country |
+----+---------------+---------------------------+-------+---------+
|  1 | Google        | https://www.google.cm/    |     1 | USA     |
|  2 | 淘宝          | https://www.taobao.com/   |    13 | CN      |
|  3 | 菜鸟教程       | http://www.runoob.com/    |  5000 | USA     |
|  4 | 微博           | http://weibo.com/         |    20 | CN      |
|  5 | Facebook      | https://www.facebook.com/ |     3 | USA     |
|  7 | stackoverflow | http://stackoverflow.com/ |     0 | IND     |
+----+---------------+---------------------------+-------+---------+
```
## 列的别名实例
下面的 SQL 语句指定了两个别名，一个是 name 列的别名，一个是 country 列的别名。提示：如果列名称包含空格，要求使用双引号或方括号：
> SELECT name AS n, country AS c
> FROM Websites;

![image](https://user-images.githubusercontent.com/18340126/163328407-fcae1031-a628-40cf-864e-1e552b20087d.png)

在下面的 SQL 语句中，我们把三个列（url、alexa 和 country）结合在一起，并创建一个名为 "site_info" 的别名：
> SELECT name, CONCAT(url, ', ', alexa, ', ', country) AS site_info
> FROM Websites;
![image](https://user-images.githubusercontent.com/18340126/163328479-a1a230a8-0036-4078-964c-44b1c1b9e301.png)

## 表的别名实例
下面的 SQL 语句选取 "菜鸟教程" 的所有访问记录。我们使用 "Websites" 和 "access_log" 表，并分别为它们指定表别名 "w" 和 "a"（通过使用别名让 SQL 更简短）：

> SELECT w.name, w.url, a.count, a.date
> FROM Websites AS w, access_log AS a
> WHERE a.site_id=w.id and w.name="菜鸟教程";
执行输出结果：
![image](https://user-images.githubusercontent.com/18340126/163328581-b356f536-52d9-41d8-b291-04d8db9d6702.png)

不带别名的相同的 SQL 语句：
> SELECT Websites.name, Websites.url, access_log.count, access_log.date
> FROM Websites, access_log
> WHERE Websites.id=access_log.site_id and Websites.name="菜鸟教程";

执行输出结果：
![image](https://user-images.githubusercontent.com/18340126/163328667-bf756639-7146-47c7-8169-61b2e2a185c3.png)

在下面的情况下，使用别名很有用：

- 在查询中涉及超过一个表
- 在查询中使用了函数
- 列名称很长或者可读性差
- 需要把两个列或者多个列结合在一起


