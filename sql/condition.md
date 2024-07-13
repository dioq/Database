# 条件

## 匹配符号

=                                 准确匹配
like, not like                    模糊匹配

## 模糊匹配

like  匹配(not like 是like 的相反值)

通配符                                描述
_                                 匹配任何单个字符
%                                 匹配任意数目字符(包括零个字符)

例如:
select * from table where post_name like '%hello%';
