# SQL GROUP BY 语句
GROUP BY 语句可结合一些聚合函数来使用

## GROUP BY 语句
GROUP BY 语句用于结合聚合函数，根据一个或多个列对结果集进行分组。
### SQL GROUP BY 语法
```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
WHERE column_name operator value
GROUP BY column_name;

```

## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "Websites" 表的数据：



| id    |name     |url        |alexa      |country    |
| :---- | :------ | :-------- | :-------- | :-------- |
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝          | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程      | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博          | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |
| 7  | stackoverflow | http://stackoverflow.com/ |   0 | IND     |

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

## GROUP BY 简单应用

统计 access_log 各个 site_id 的访问量：

```sql
SELECT site_id, SUM(access_log.count) AS nums
FROM access_log GROUP BY site_id;

```
执行以上 SQL 输出结果如下：
![image](https://user-images.githubusercontent.com/18340126/173325125-4463ffdb-4776-44c9-852f-8da88a52801b.png)

## SQL GROUP BY 多表连接
下面的 SQL 语句统计有记录的网站的记录数量：

```sql
SELECT Websites.name,COUNT(access_log.aid) AS nums FROM access_log
LEFT JOIN Websites
ON access_log.site_id=Websites.id
GROUP BY Websites.name;

```

执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/173325344-9faac548-cc3b-447f-a001-e0b81ecf7342.png)


