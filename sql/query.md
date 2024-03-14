# query 查询数据

## 语法

查询 column1, column2, column3,...columnN 数据
select column1, column2, column3,...columnN from TABLE_NAME;

## * 匹配所有

查询数据的所有列
select * from TABLE_NAME;

## count 数据行数

select count(*) from TABLE_NAME;

## limit 限制返回条数

select * from TABLE_NAME limit 100;

## hex 二进制数据以 16进制字符串的形式显示

select hex(column) from TABLE_NAME where [condition];

## 实例

select ID, NAME, SALARY from COMPANY;
查询条数
select count(*) from keychain where remarks = 'wechatbackup';

hex 2进制数据以 16进制字符串的形式显示
select hex(acct) from genp where agrp == "5YBWG2X244.cn.jobs8.keychain";
