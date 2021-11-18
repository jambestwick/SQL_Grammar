SQL INSERT INTO 语句
INSERT INTO 语句用于向表中插入新记录。

SQL INSERT INTO 语句
INSERT INTO 语句用于向表中插入新记录。

SQL INSERT INTO 语法
INSERT INTO 语句可以有两种编写形式。

第一种形式无需指定要插入数据的列名，只需提供被插入的值即可：

INSERT INTO table_name
VALUES (value1,value2,value3,...);
第二种形式需要指定列名及被插入的值：

INSERT INTO table_name (column1,column2,column3,...)
VALUES (value1,value2,value3,...);

演示数据库
在本教程中，我们将使用 RUNOOB 样本数据库。

下面是选自 "Websites" 表的数据：

+----+--------------+---------------------------+-------+---------+
| id | name         | url                       | alexa | country |
+----+--------------+---------------------------+-------+---------+
| 1  | Google       | https://www.google.cm/    | 1     | USA     |
| 2  | 淘宝          | https://www.taobao.com/   | 13    | CN      |
| 3  | 菜鸟教程      | http://www.runoob.com/    | 4689  | CN      |
| 4  | 微博          | http://weibo.com/         | 20    | CN      |
| 5  | Facebook     | https://www.facebook.com/ | 3     | USA     |
+----+--------------+---------------------------+-------+---------+
INSERT INTO 实例
假设我们要向 "Websites" 表中插入一个新行。

我们可以使用下面的 SQL 语句：

实例
INSERT INTO Websites (name, url, alexa, country)
VALUES ('百度','https://www.baidu.com/','4','CN');
执行以上 SQL，再读取 "Websites" 表，数据如下所示：



lamp	您是否注意到，我们没有向 id 字段插入任何数字？
id 列是自动更新的，表中的每条记录都有一个唯一的数字。

在指定的列插入数据
我们也可以在指定的列插入数据。

下面的 SQL 语句将插入一个新行，但是只在 "name"、"url" 和 "country" 列插入数据（id 字段会自动更新）：

实例
INSERT INTO Websites (name, url, country)
VALUES ('stackoverflow', 'http://stackoverflow.com/', 'IND');
执行以上 SQL，再读取 "Websites" 表，数据如下所示：

