# SQL SUM() 函数
## SUM() 函数
SUM() 函数返回数值列的总数。

### SQL SUM() 语法
```sql
SELECT SUM(column_name) FROM table_name;

```
### 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "access_log" 表的数据：

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

## SQL SUM() 实例
下面的 SQL 语句查找 "access_log" 表的 "count" 字段的总数：

实例

```sql
SELECT SUM(count) AS nums FROM access_log;
```

执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/173321671-959c6b4c-7a7a-4fce-b56c-68e057972609.png)
