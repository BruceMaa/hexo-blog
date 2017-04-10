---
title: MySQL使用记录－－函数篇
category: Technology
tags:
- Database
- MySQL
---

## 记录MySQL的函数

> 用到一个，遇到一个，就记录一个，不必特意收集

### 运算函数

#### MOD

> 取余数
> 
- MOD(N, M)
- N % M
- N MOD M

```
mysql> SELECT MOD(234, 10);
		-> 4
mysql> SELECT 253 % 7;
		-> 1
mysql> SELECT MOD(29, 9);
		-> 2
mysql> SELECT 29 MOD 9;
		-> 2
mysql> SELECT MOD(34.5, 3);
		-> 1.5
mysql> SELECT MOD(2, 0);
		-> NULL
```

<!-- more -->

### 分组函数

#### GROUP_CONCAT

> 这个函数通过``group by``分组，把所有非NULL值串联成一个字符串。如果没有非NULL值，则返回NULL，语法如下：

```sql
	GROUP_CONCAT([DISTINCT] expr [, expr ...]
					[ORDER BY {unsigned_integer | col_name | expr}
						[ASC | DESC] [,col_name ...]]
					[SEPARATOR str_val])
```

***

```sql
mysql> SELECT student_name,
     ->	GROUP_CONCAT(test_score)
     ->	FROM student
     ->	GROUP BY student_name;
```

或者：

```sql
mysql> SELECT student_name,
		->		GROUP_CONCAT(DISTINCT test_score ORDER BY test_score DESC SEPARATOR ' ')
		->		FROM student
		->		GROUP BY student_name;
```

> 在MySQL中，你可以获取表达式串联的值。使用``DISTINCT``关键字去掉重复的值。使用``ORDER BY``关键字排序结果。串联值的默认分隔符是逗号``,``，如果要使用其它分隔符，则需要使用``SEPARATOR``声明。
> 
> 返回的字符串最大长度，是通过参数``group_concat_max_len``设置的，默认为1024。也可以设置更大的值，虽然回归值的有效最大长度由参数``max_allowed_packet``设置。运行时设置``group_concat_max_len``参数的语法如下，``val``是一个非负整数：

```
SET [GLOBAL | SESSION] group_concat_max_len = val;
```

> 如果``group_concat_max_len``设置的长度小于等于512，则返回类型是``VARCHAR``或者``VARBINARY``，否则返回类型是``TEXT``或``BLOB``。
