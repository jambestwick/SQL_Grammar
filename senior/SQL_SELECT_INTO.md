# SQL SELECT INTO 语句
通过 SQL，您可以从一个表复制信息到另一个表。

SELECT INTO 语句从一个表复制数据，然后把数据插入到另一个新表中。

## SQL SELECT INTO 语句
SELECT INTO 语句从一个表复制数据，然后把数据插入到另一个新表中。

*注意*：

MySQL 数据库不支持 SELECT ... INTO 语句，但支持 INSERT INTO ... SELECT 。

当然你可以使用以下语句来拷贝表结构及数据：
```
CREATE TABLE 新表
AS
SELECT * FROM 旧表
```
### SQL SELECT INTO 语法
我们可以复制所有的列插入到新表中：
```
SELECT *
INTO newtable [IN externaldb]
FROM table1;
```
或者只复制希望的列插入到新表中：
```
SELECT column_name(s)
INTO newtable [IN externaldb]
FROM table1;
```

💡	
**提示**：新表将会使用 SELECT 语句中定义的列名称和类型进行创建。您可以使用 AS 子句来应用新名称。


## SQL SELECT INTO 实例
创建 Websites 的备份复件：
```
SELECT *
INTO WebsitesBackup2016
FROM Websites;
```
只复制一些列插入到新表中：
```
SELECT name, url
INTO WebsitesBackup2016
FROM Websites;
```
只复制中国的网站插入到新表中：
```
SELECT *
INTO WebsitesBackup2016
FROM Websites
WHERE country='CN';
```
复制多个表中的数据插入到新表中：

```
SELECT Websites.name, access_log.count, access_log.date
INTO WebsitesBackup2016
FROM Websites
LEFT JOIN access_log
ON Websites.id=access_log.site_id;
```
**提示**：SELECT INTO 语句可用于通过另一种模式创建一个新的空表。只需要添加促使查询没有数据返回的 WHERE 子句即可：
```
SELECT *
INTO newtable
FROM table1
WHERE 1=0;
```
