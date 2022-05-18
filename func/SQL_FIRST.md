# SQL FIRST() 函数

## FIRST() 函数

FIRST() 函数返回指定的列中第一个记录的值。

### SQL FIRST() 语法

```sql
SELECT FIRST(column_name) FROM table_name;
```
**注释**：只有 MS Access 支持 FIRST() 函数。

## SQL Server、MySQL 和 Oracle 中的 SQL FIRST() 工作区

### SQL Server 语法

```sql
SELECT TOP 1 column_name FROM table_name
ORDER BY column_name ASC;
```
### 实例
```sql
SELECT TOP 1 name FROM Websites
ORDER BY id ASC;
```
### MySQL 语法
```sql
SELECT column_name FROM table_name
ORDER BY column_name ASC
LIMIT 1;
```
### 实例
```sql
SELECT name FROM Websites
ORDER BY id ASC
LIMIT 1;
```

### Oracle 语法
```sql
SELECT column_name FROM table_name
ORDER BY column_name ASC
WHERE ROWNUM <=1;
```
### 实例
```sql
SELECT name FROM Websites
ORDER BY id ASC
WHERE ROWNUM <=1;

```

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
|  6 | 百度         | https://www.baidu.com/    |     4 | CN      |
|  7 | stackoverflow | http://stackoverflow.com/ |     0 | IND     |
+----+---------------+---------------------------+-------+---------+
```

## SQL FIRST() 实例

下面的 SQL 语句选取 "Websites" 表的 "name" 列中第一个记录的值：

实例
```sql
SELECT name AS FirstSite FROM Websites LIMIT 1;
```
![limit1](https://user-images.githubusercontent.com/18340126/168981006-3804fa91-4cae-420c-a145-f8e90d55e5c7.jpg)

