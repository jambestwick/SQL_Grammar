### 在搜索数据库中的数据时，您可以使用 SQL 通配符。
## SQL 通配符
在搜索数据库中的数据时，SQL 通配符可以替代一个或多个字符。

SQL 通配符必须与 LIKE 运算符一起使用。

在 SQL 中，可使用以下通配符：

| 通配符 | 	 |	FirstName |	Address |	City |
| --------:   | :-----:  |
| %	| 代表零个或多个字符 |
| _	| 仅替代一个字符 |
| [charlist]	| 字符列中的任何单一字符 |
| [^charlist]

或者

[!charlist]	| 不在字符列中的任何单一字符 |
## 原始的表 (用在例子中的)：
Persons 表:

| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 1	| Adams	| John	| Oxford | Street	| London |
| 2	| Bush	| George	| Fifth | Avenue	| New York |
| 3	| Carter |Thomas	| Changan | Street	| Beijing |

## 使用 % 通配符
### 例子 1
现在，我们希望从上面的 "Persons" 表中选取居住在以 "Ne" 开始的城市里的人：

我们可以使用下面的 SELECT 语句：
> SELECT * FROM Persons
> WHERE City LIKE 'Ne%'

### 结果集：

| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 2 |	Bush |	George |	Fifth | Avenue |	New | York |

### 例子 2
接下来，我们希望从 "Persons" 表中选取居住在包含 "lond" 的城市里的人：

我们可以使用下面的 SELECT 语句：

> SELECT * FROM Persons
> WHERE City LIKE '%lond%'

### 结果集：
| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 1 |	Adams	| John | Oxford | Street | London |

## 使用 _ 通配符
### 例子 1
现在，我们希望从上面的 "Persons" 表中选取名字的第一个字符之后是 "eorge" 的人：

我们可以使用下面的 SELECT 语句：
> SELECT * FROM Persons
> WHERE FirstName LIKE '_eorge'

### 结果集
| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 2 |	Bush |	George |	Fifth | Avenue |	New | York |
### 例子 2
接下来，我们希望从 "Persons" 表中选取的这条记录的姓氏以 "C" 开头，然后是一个任意字符，然后是 "r"，然后是一个任意字符，然后是 "er"：

我们可以使用下面的 SELECT 语句：
> SELECT * FROM Persons
> WHERE LastName LIKE 'C_r_er'
### 结果集：
| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 3	| Carter |Thomas	| Changan | Street	| Beijing |

## 使用 [charlist] 通配符
### 例子 1
现在，我们希望从上面的 "Persons" 表中选取居住的城市以 "A" 或 "L" 或 "N" 开头的人：

我们可以使用下面的 SELECT 语句：
> SELECT * FROM Persons
> WHERE City LIKE '[ALN]%'
### 结果集：
 | Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 1	| Adams	| John	| Oxford | Street	| London |
| 2	| Bush	| George	| Fifth | Avenue	| New York |
### 例子 2
现在，我们希望从上面的 "Persons" 表中选取居住的城市不以 "A" 或 "L" 或 "N" 开头的人：

我们可以使用下面的 SELECT 语句：
> SELECT * FROM Persons
> WHERE City LIKE '[!ALN]%'

### 结果集：
| Id | 	LastName |	FirstName |	Address |	City |
| --------:   | :-----:  | :----:  |:----:  |----:  |
| 3	| Carter |Thomas	| Changan | Street	| Beijing |
