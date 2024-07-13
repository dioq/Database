# SQLite 数据库

SQLite数据库存储在单机单文件,一个.sqlite文件就包含了SQLite数据库所有的东西

## CLI 操作 SQLite

sqlite3 /path/[name].db                     -- 创建或打开数据库(数据库存在打开数据库,不存在就先创建后再打开)
.quit                                       -- 退出 CLI
.tables                                     -- 展示所有表
.schema TABLE_NAME                          -- 查询表结构
.header on                                  -- 格式化 输出的 cloumn name
.mode column                                -- 格式化 输出的 cloumn value

## SQLite 存储类

存储类                          描述
NULL                          NULL 值
INTEGER                       带符号的整数,根据值的大小存储在 1、2、3、4、6 或 8 字节中
REAL                          浮点值,存储为 8 字节的 IEEE 浮点数字
TEXT                          文本字符串,使用数据库编码（UTF-8、UTF-16BE 或 UTF-16LE）存储,最大长度可达到 1G
BLOB                          blob 数据,完全根据它的输入存储

## SQLite 时间

函数                                                            实例
date(timestring, modifier, modifier, ...)                  YYYY-MM-DD 格式返回日期
time(timestring, modifier, modifier, ...)                  HH:MM:SS 格式返回时间
datetime(timestring, modifier, modifier, ...)              YYYY-MM-DD HH:MM:SS 格式返回
