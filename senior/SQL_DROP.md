# SQL 撤销索引、撤销表以及撤销数据库
通过使用 DROP 语句，可以轻松地删除索引、表和数据库。

## DROP INDEX 语句

DROP INDEX 语句用于删除表中的索引。

### 用于 MS Access 的 DROP INDEX 语法：

```sql
DROP INDEX index_name ON table_name

```
### 用于 MS SQL Server 的 DROP INDEX 语法：
```sql
DROP INDEX table_name.index_name

```
### 用于 DB2/Oracle 的 DROP INDEX 语法：
```sql
DROP INDEX index_name

```

### 用于 MySQL 的 DROP INDEX 语法：
```sql
ALTER TABLE table_name DROP INDEX index_name

```

## DROP TABLE 语句

DROP TABLE 语句用于删除表。
```sql
DROP DATABASE database_name

```

## TRUNCATE TABLE 语句

如果我们仅仅需要删除表内的数据，但并不删除表本身，那么我们该如何做呢？

请使用 TRUNCATE TABLE 语句：

```sql
TRUNCATE TABLE table_name

```
