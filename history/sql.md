# sql 语句

创建表
create table app_data
(
    id           integer primary key autoincrement,
    createtime   datetime default (datetime('now', 'localtime')),
    updatetime   datetime default (datetime('now', 'localtime')),
    bundle_id    text not null,
    storage_name text not null,
    display_name text,
    keychain     text,
    size         integer default 0
);

insert into app_data (bundle_id,storage_name,display_name) values ("com.tencent.xin","UUUU-ddddd","wxid_01")

时间同步
update app_data set package_name = '微信',updatetime = datetime('now', 'localtime')  where package_name == 'wechat';

排序
SELECT * FROM app_data ORDER BY updatetime;
降序
SELECT * FROM app_data ORDER BY updatetime DESC;

去重
select distinct bundle_id from app_data;

insert into app_data (bundle_id,storage_name,display_name) values ("com.wechat.qq","w4");
update app_data set display_name = '微信',updatetime = datetime('now', 'localtime')  where package_name == 'wechat';
SELECT * FROM app_data ORDER BY updatetime;
SELECT * FROM app_data where bundle_id = "cn.jobs8.TargetForBackup" ORDER BY updatetime DESC;
select distinct bundle_id from app_data;

insert into app_data (bundle_id,storage_name,display_name,size) values ("com.tencent.xin","UUUU-ddddd","wxid_01",1000)
