# query

## 语法

select column1, column2, column3,...columnN from TABLE_NAME;
从 TABLE_NAME 表 查询 column1, column2, column3,...columnN 数据

## 查询操作

### 返回 column 内容设置

`*`                                             匹配所有 column
count([column])                                 数据行数
hex([column])                                   二进制数据以 16进制字符串的形式显示
distinct [column]                               去除重复项

### 返回 column 结果设置

limit [number]                                  限制返回条数
ORDER BY [column]                               根据 column 排列(升序)
ORDER BY [column] DESC                          根据 column 降序排列

例如:
select *from TABLE_NAME;                            -- 返回数据的所有列
select count(*) from TABLE_NAME;                    -- 返回数据行数
select * from TABLE_NAME limit 100;                 -- 返回 100 列
select hex(column) from TABLE_NAME where [condition];       -- 二进制数据以 16进制字符串的形式显示
select distinct bundle_id from app_data;            -- bundle_id 种类
