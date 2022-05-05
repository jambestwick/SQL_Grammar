# SQL UNION 操作符
SQL UNION 操作符合并两个或多个 SELECT 语句的结果。

## SQL UNION 操作符
UNION 操作符用于合并两个或多个 SELECT 语句的结果集。

请注意，UNION 内部的每个 SELECT 语句必须拥有相同数量的列。列也必须拥有相似的数据类型。同时，每个 SELECT 语句中的列的顺序必须相同。

### SQL UNION 语法
```
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```
**注释**：默认地，UNION 操作符选取不同的值。如果允许重复的值，请使用 UNION ALL。

### SQL UNION ALL 语法
```
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```
**注释**：UNION 结果集中的列名总是等于 UNION 中第一个 SELECT 语句中的列名。

### 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "Websites" 表的数据：

```
mysql> SELECT * FROM Websites;
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
下面是 "apps" APP 的数据：
```
mysql> SELECT * FROM apps;
+----+------------+-------------------------+---------+
| id | app_name   | url                     | country |
+----+------------+-------------------------+---------+
|  1 | QQ APP     | http://im.qq.com/       | CN      |
|  2 | 微博 APP | http://weibo.com/       | CN      |
|  3 | 淘宝 APP | https://www.taobao.com/ | CN      |
+----+------------+-------------------------+---------+
3 rows in set (0.00 sec)
```

## SQL UNION 实例
下面的 SQL 语句从 "Websites" 和 "apps" 表中选取所有**不同的**country（只有不同的值）：

实例
> SELECT country FROM Websites
> UNION
> SELECT country FROM apps
> ORDER BY country;
执行以上 SQL 输出结果如下：
![image](https://user-images.githubusercontent.com/18340126/163333515-aa2e9d64-80d0-45a0-b3ca-13cc816afe3d.png)


**注释**：UNION 不能用于列出两个表中所有的country。如果一些网站和APP来自同一个国家，每个国家只会列出一次。UNION 只会选取不同的值。请使用 UNION ALL 来选取重复的值！

## SQL UNION ALL 实例
下面的 SQL 语句使用 UNION ALL 从 "Websites" 和 "apps" 表中选取所有的country（也有重复的值）：

实例
> SELECT country FROM Websites
> UNION ALL
> SELECT country FROM apps
> ORDER BY country;
执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/163333615-15276329-c254-45e6-84da-72c065bfabec.png)


## 带有 WHERE 的 SQL UNION ALL
下面的 SQL 语句使用 UNION ALL 从 "Websites" 和 "apps" 表中选取所有的中国(CN)的数据（也有重复的值）：

实例
> SELECT country, name FROM Websites
> WHERE country='CN'
> UNION ALL
> SELECT country, app_name FROM apps
> WHERE country='CN'
> ORDER BY country;
执行以上 SQL 输出结果如下：
![image](https://user-images.githubusercontent.com/18340126/163333756-e4135942-853b-418a-b761-0fa021f04db7.png)

