# sqlite 数据库

## 创建数据库(如果数据库已经存在就进入数据库)

sqlite3 database_name
实例:
sqlite3 my.db

## 退出操作

sqlite>.quit

## 创建表

sqlite> create table table_name(
   column1 datatype  PRIMARY KEY(one or more columns),
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
);
实例:
sqlite> create table keychain(
   id integer primary key autoincrement, -- 创建主键并自增
   bundleid text not null unique, --  bundleid 不能为空且唯一
   account text not null,
   mark text,
   createtime datetime not null, -- 创建时间
   updatetime datetime default (datetime('now', 'localtime')), -- 更新时间 自动添加当前时间
   genp text, -- text 最大长度可达到 1G
   inet text,
   cert text,
   keys text,
   idnt text
);

## 操作数据库表

查询所有的表
sqlite>.tables
查询表的完整信息
sqlite>.schema table_name
删除表
sqlite>drop table table_name;

## 插入数据

insert into TABLE_NAME (column1, column2, column3,...columnN)
values (value1, value2, value3,...valueN);
实例:
sqlite> insert into COMPANY (ID,NAME,AGE,ADDRESS,SALARY)
values (1, 'Paul', 32, 'California', 20000.00 );

## 删除数据

delete from table_name
where [condition];
实例:
sqlite> delete from COMPANY where ID = 7;

## 清空表

delete   逐行删除速度极慢,不适合大量数据删除
delete from tablename;
drop     删除表,数据和表结构一起删除,快速
drop from tablename;

## 更新数据

update table_name
set column1 = value1, column2 = value2...., columnN = valueN
where [condition];
实例:
sqlite> update COMPANY set ADDRESS = 'Texas' where ID = 6;

## 查询

select column1, column2, columnN from table_name;
实例:
sqlite> select ID, NAME, SALARY from COMPANY;
查询并按格式化输出
sqlite> .header on
sqlite> .mode column
sqlite> select * from table_name;
