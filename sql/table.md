# table 数据库表

## create 创建表

create table TABLE_NAME(column1 type1, column2 type2, column3 type3);

column属性
column integer primary key autoincrement                 -- 主键并自增
column text                                              -- 文本字符串,最大长度可达到 1G
column text not null                                     -- 文本字符串,不能为空
column integer default 0                                 -- 有符号整数,默认值是 0
column datetime default (datetime('now', 'localtime'))   -- 时间函数,默认值是当前时间
UNIQUE(column1,column2) ON CONFLICT REPLACE              -- column1,column2 组合唯一

## drop 删除表(数据和表结构一起删除,速度极快)

drop from TABLE_NAME;

## truncate 清空表(保留表结构)

truncate TABLE_NAME;
