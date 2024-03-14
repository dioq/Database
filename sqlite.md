# sqlite 数据库

## 创建或打开数据库(数据库存在打开数据库,不存在就创建)

sqlite3 DATABASE_PATH
实例: sqlite3 my.db

## 退出操作

sqlite>.quit

## 表信息

展示所有表
sqlite>.tables
查询表结构
sqlite>.schema TABLE_NAME

## 格式化输出

sqlite>.header on
sqlite>.mode column
