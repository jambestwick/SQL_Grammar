## SQL BETWEEN 操作符
### BETWEEN 操作符

BETWEEN 操作符选取介于两个值之间的数据范围内的值。这些值可以是数值、文本或者日期。

### SQL BETWEEN 语法

> SELECT column_name(s)
> FROM table_name
> WHERE column_name BETWEEN value1 AND value2;

### 演示数据库 (在实例中使用：)
下面的 SQL 语句选取 alexa 介于 1 和 20 之间的所有网站

SELECT * FROM Websites
WHERE alexa BETWEEN 1 AND 20;

![btw1](https://user-images.githubusercontent.com/18340126/163326953-4e6f01ae-1bd6-42f8-bf42-cb9c7cc72592.jpg)

### NOT BETWEEN 操作符实例
如需显示不在上面实例范围内的网站，请使用 NOT BETWEEN：
SELECT * FROM Websites
WHERE alexa NOT BETWEEN 1 AND 20;

![image](https://user-images.githubusercontent.com/18340126/163327059-aa2486da-34fe-4268-93c7-de6c07e344be.png)

### 带有 IN 的 BETWEEN 操作符实例
下面的 SQL 语句选取 alexa 介于 1 和 20 之间但 country 不为 USA 和 IND 的所有网站：

SELECT * FROM Websites
WHERE (alexa BETWEEN 1 AND 20)
AND country NOT IN ('USA', 'IND');

![image](https://user-images.githubusercontent.com/18340126/163327145-db3ef772-2627-4f99-a94b-459cd0a4231b.png)

### 带有文本值的 BETWEEN 操作符实例
下面的 SQL 语句选取 name 以介于 'A' 和 'H' 之间字母开始的所有网站：

SELECT * FROM Websites
WHERE name BETWEEN 'A' AND 'H';

![image](https://user-images.githubusercontent.com/18340126/163327213-dfae051f-5ffc-4eba-87b0-40a31f6cda05.png)

### 带有文本值的 NOT BETWEEN 操作符实例
下面的 SQL 语句选取 name 不介于 'A' 和 'H' 之间字母开始的所有网站：

SELECT * FROM Websites
WHERE name NOT BETWEEN 'A' AND 'H';

![image](https://user-images.githubusercontent.com/18340126/163327292-64d15955-576e-4115-8862-39131d63965f.png)

### 示例表
下面是 "access_log" 网站访问记录表的数据，其中：

- aid：为自增 id。
- site_id：为对应 websites表的网站 id。
- count：访问次数。
- date：为访问日期。
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

### 带有日期值的 BETWEEN 操作符实例
下面的 SQL 语句选取 date 介于 '2016-05-10' 和 '2016-05-14' 之间的所有访问记录：

SELECT * FROM access_log
WHERE date BETWEEN '2016-05-10' AND '2016-05-14';

![image](https://user-images.githubusercontent.com/18340126/163327751-dc7a37a7-4563-41dd-b07b-e8ba18ea360e.png)

:lamp	
请注意，在不同的数据库中，BETWEEN 操作符会产生不同的结果！
在某些数据库中，BETWEEN 选取介于两个值之间但不包括两个测试值的字段。
在某些数据库中，BETWEEN 选取介于两个值之间且包括两个测试值的字段。
在某些数据库中，BETWEEN 选取介于两个值之间且包括第一个测试值但不包括最后一个测试值的字段。

因此，请检查您的数据库是如何处理 BETWEEN 操作符！
