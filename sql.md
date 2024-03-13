# sql语句

sql删除或清空表数据
一、sql清空表数据的三种方式:
1、truncate 删除所有数据，保留表结构，不能撤销还原
2、delete 是逐行删除速度极慢，不适合大量数据删除
3、drop 删除表，数据和表结构一起删除，快速
二、语法
delete from 表名
delete from 表名 where 列名="value"
drop from 表名

create table keychain(
   id integer primary key autoincrement, -- 创建主键并自增
   remarks text not null,
   updatetime datetime default (datetime('now', 'localtime')), -- 更新时间 自动添加当前时间
   data text -- text 最大长度可达到 1G
);
insert into keychain (remarks,data) values("backup wechat","this is only a test","{gent}");
update keychain set data = 'new test 2' where remarks = "backup wechat";

查询有多少条数据
select count(*) from keychain where remarks = 'wechatbackup';

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

CREATE TABLE IF NOT EXISTS target (
   id integer PRIMARY KEY AUTOINCREMENT,
   target_bundle_id text NOT NULL,
   assistant_version text NOT NULL,
   delete_files text NOT NULL,
   backup_files text NOT NULL,
   remark text,
   UNIQUE(target_bundle_id,assistant_version) ON CONFLICT REPLACE
);

hex 2进制数据以 16进制字符串的形式显示
select hex(acct) from genp where agrp == "5YBWG2X244.cn.jobs8.keychain";

limit 限制返回条数
select hex(acct) from genp limit n;