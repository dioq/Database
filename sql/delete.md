# delete 删除数据

## delete 以行为单位删除数据行

delete from TABLE_NAME where [condition];
delete from TABLE_NAME;             # 不添加条件就删除表里所有数据,速度极慢不适合大量数据删除
