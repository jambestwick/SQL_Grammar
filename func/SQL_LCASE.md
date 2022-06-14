# SQL LCASE() 函数
## LCASE() 函数
LCASE() 函数把字段的值转换为小写。
### SQL LCASE() 语法
```sql
SELECT LCASE(column_name) FROM table_name;

```
用于 SQL Server 的语法

```sql
SELECT LOWER(column_name) FROM table_name;
```

## 演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "Websites" 表的数据：


| id | name         | url                       | alexa | country |
|----|--------------|---------------------------|-------|---------|
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝          | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程      | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博          | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |
| 7  | stackoverflow | http://stackoverflow.com/ |   0 | IND     |

## SQL LCASE() 实例
下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "url" 列，并把 "name" 列的值转换为小写：
实例
```sql

SELECT LCASE(name) AS site_title, url
FROM Websites;
```

执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/173590099-aa54f9fa-1436-4a83-a895-29a292370ddb.png)
