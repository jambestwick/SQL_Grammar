  # SQL FORMAT() 函数
  ## FORMAT() 函数
  FORMAT() 函数用于对字段的显示进行格式化。
  
 ### SQL FORMAT() 语法
 ```sql
 SELECT FORMAT(column_name,format) FROM table_name;
 
 ```
 
 |参数|	描述|
 |----|----|
|column_name|	必需。要格式化的字段。|
|format|	必需。规定格式。|

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

## SQL FORMAT() 实例
下面的 SQL 语句从 "Websites" 表中选取 name, url 以及格式化为 YYYY-MM-DD 的日期：

实例
```sql
SELECT name, url, DATE_FORMAT(Now(),'%Y-%m-%d') AS date
FROM Websites;
```
执行以上 SQL 输出结果如下：
![image](https://user-images.githubusercontent.com/18340126/177558976-da3772aa-6903-4288-acae-65ae74a8ecbd.png)


