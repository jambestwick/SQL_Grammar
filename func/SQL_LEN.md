# SQL LEN() 函数
## LEN() 函数
LEN() 函数返回文本字段中值的长度。
### SQL LEN() 语法
```sql
SELECT LEN(column_name) FROM table_name;

```
MySQL 中函数为 LENGTH():
```sql
SELECT LENGTH(column_name) FROM table_name;
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


## SQL LEN() 实例

下面的 SQL 语句从 "Websites" 表中选取 "name" 和 "url" 列中值的长度：
```sql
SELECT name, LENGTH(url) as LengthOfURL
FROM Websites;
```
执行以上 SQL 输出结果如下：
![image](https://user-images.githubusercontent.com/18340126/174988251-a9b9d73d-d13f-4f2f-ae4f-905c6998a135.png)
