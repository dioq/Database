# table 数据库表

## create 创建表

create table TABLE_NAME(column1 type1, column2 type2, column3 type3);

## drop 删除表(数据和表结构一起删除,速度极快)

drop from TABLE_NAME;

## truncate 清空表,保留表结构

truncate TABLE_NAME;

## 实例

create table keychain(
   id integer primary key autoincrement, -- 创建主键并自增
   remarks text not null,
   updatetime datetime default (datetime('now', 'localtime')), -- 更新时间 自动添加当前时间
   data text -- text 最大长度可达到 1G
);

CREATE TABLE IF NOT EXISTS app_data (
   id integer PRIMARY KEY AUTOINCREMENT,
   bundle_id text NOT NULL,
   account_id text NOT NULL,
   phone_num text,
   passwords text,
   remark text,
   keychain_data text,
   files_data text,
   device_name text,
   idfa text,
   os_index integer,
   UNIQUE(bundle_id,account_id) ON CONFLICT REPLACE       -- bundle_id,account_id 组成的联合体不重复
);
