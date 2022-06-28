# SQL ROUND() 函数
## ROUND() 函数
ROUND() 函数用于把数值字段舍入为指定的小数位数。
### SQL ROUND() 语法
```sql
SELECT ROUND(column_name,decimals) FROM TABLE_NAME;

```

|参数	|描述|
|-----|----|
|column_name	|必需。要舍入的字段。|
|decimals	|可选。规定要返回的小数位数。|

## SQL ROUND() 实例
**ROUND(X)**： 返回参数X的四舍五入的一个整数。

```sql
mysql> SELECT ROUND(-1.23);
        -> -1
mysql> SELECT ROUND(-1.58);
        -> -2
mysql> SELECT ROUND(1.58);
        -> 2
```

**ROUND(X,D):** 返回参数X的四舍五入的有 D 位小数的一个数字。如果D为0，结果将没有小数点或小数部分。

```sql
mysql> SELECT ROUND(1.298, 1);
        -> 1.3
mysql> SELECT ROUND(1.298, 0);
        -> 1

```
