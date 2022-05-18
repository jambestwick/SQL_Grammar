# SQL AVG() 函数
## AVG() 函数
AVG() 函数返回数值列的平均值。
### SQL AVG() 语法
```sql
SELECT AVG(column_name) FROM table_name
```
## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "access_log" 表的数据：

```
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
```

## SQL AVG() 实例
下面的 SQL 语句从 "access_log" 表的 "count" 列获取平均值：

```sql
SELECT AVG(count) AS CountAverage FROM access_log;
```
执行以上 SQL 输出结果如下：


![avg1](https://user-images.githubusercontent.com/18340126/168978885-a7bd2435-fba1-4eef-a769-c5494fa23d05.jpg)
下面的 SQL 语句选择访问量高于平均访问量的 "site_id" 和 "count"：

实例
```sql
SELECT site_id, count FROM access_log
WHERE count > (SELECT AVG(count) FROM access_log);
```
![avg2](https://user-images.githubusercontent.com/18340126/168978997-17bb8399-aeff-4b55-bc5c-a269f5dee654.jpg)

