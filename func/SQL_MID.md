# SQL MID() 函数
## MID() 函数
MID() 函数用于从文本字段中提取字符。
### SQL MID() 语法
```sql
SELECT MID(column_name,start[,length]) FROM table_name;

```

|参数  |描述    |
|:----:|:-----:|
|column_name	|必需。要提取字符的字段。|
|start	|必需。规定开始位置（起始值是 1）。|
|length	|可选。要返回的字符数。如果省略，则 MID() 函数返回剩余文本。|

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

## SQL MID() 实例
下面的 SQL 语句从 "Websites" 表的 "name" 列中提取前 4 个字符：
实例
```sql
SELECT MID(name,1,4) AS ShortTitle
FROM Websites;
```
执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/174221620-70b91695-2ebe-4a46-a006-9027e4af1242.png)
