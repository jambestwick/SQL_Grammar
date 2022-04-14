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

![](https://www.runoob.com/wp-content/uploads/2013/09/btw1.jpg)

Persons 表:

| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 1	| Adams	| John	| Oxford | Street	| London |
| 2	| Bush	| George	| Fifth | Avenue	| New York |
| 3	| Carter |Thomas	| Changan | Street	| Beijing |

### IN 操作符实例
现在，我们希望从上表中选取姓氏为 Adams 和 Carter 的人：

我们可以使用下面的 SELECT 语句：
> SELECT * FROM Persons
> WHERE LastName IN ('Adams','Carter')

### 结果集：

| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 1 |	Adams	| John | Oxford | Street | London |
| 3	| Carter |Thomas	| Changan | Street	| Beijing |
