# SQL SELECT 语句
SELECT 语句用于从数据库中选取数据。
结果被存储在一个结果表中，称为结果集。

## SQL SELECT 语法
---
 SELECT column_name,column_name FROM table_name;
---
与
---
 SELECT * FROM table_name;
---
## 演示数据库

下面是选自 "Websites" 表的数据：
```
+----+--------------+---------------------------+-------+---------+
| id | name         | url                       | alexa | country |
+----+--------------+---------------------------+-------+---------+
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝          | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程      | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博          | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |
+----+--------------+---------------------------+-------+---------+
```
## SELECT Column 实例
下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "country" 列：


> SELECT name,country FROM Websites;
输出结果为:
![pic](https://www.runoob.com/wp-content/uploads/2013/09/98E6B49C-06AF-469B-B907-81C52BBE6BDC.jpg)

