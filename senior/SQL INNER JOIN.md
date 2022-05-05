# SQL INNER JOIN 关键字
## SQL INNER JOIN 关键字
INNER JOIN 关键字在表中存在至少一个匹配时返回行。
### SQL INNER JOIN 语法
```
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name=table2.column_name;
```
或
```
SELECT column_name(s)
FROM table1
JOIN table2
ON table1.column_name=table2.column_name;
```
**注释**：INNER JOIN 与 JOIN 是相同的。
![image](https://user-images.githubusercontent.com/18340126/163330403-379fdbb3-f9cf-4a90-995d-6fd788e9c8d1.png)

## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

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
## SQL INNER JOIN 实例
下面的 SQL 语句将返回所有网站的访问记录：
> 实例
> SELECT Websites.name, access_log.count, access_log.date
> FROM Websites
> INNER JOIN access_log
> ON Websites.id=access_log.site_id
> ORDER BY access_log.count;

执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/163330676-93dd229d-1cb7-4b4a-8b0b-9fa036912868.png)

**注释**：INNER JOIN 关键字在表中存在至少一个匹配时返回行。如果 "Websites" 表中的行在 "access_log" 中没有匹配，则不会列出这些行。
