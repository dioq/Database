# 查询条件

模糊匹配 like, not like
_   匹配任何单个字符
%   匹配任意数目字符(包括零个字符)

例如:
select * from table where post_name like '%hello%';
