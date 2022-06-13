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
| ----- |: ------ |: -------- |: -------- |: -------- |
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝          | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程      | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博          | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |
| 7  | stackoverflow | http://stackoverflow.com/ |   0 | IND     |
