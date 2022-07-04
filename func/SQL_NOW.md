# SQL NOW() 函数
## NOW() 函数
NOW() 函数返回当前系统的日期和时间。
### SQL NOW() 语法
```sql
SELECT NOW() FROM table_name;
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

## SQL NOW() 实例
下面的 SQL 语句从 "Websites" 表中选取 name，url，及当天日期：

实例

```sql
SELECT name, url, Now() AS date
FROM Websites;
```
执行以上 SQL 输出结果如下：

![image](https://user-images.githubusercontent.com/18340126/177119895-76ddcc2d-9b7a-4eb0-8304-568d2fa26150.png)
