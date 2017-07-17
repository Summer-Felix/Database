# [优化](https://github.com/Summer-Felix/Database/blob/master/MySQL/优化.md) #

## [Explain](http://b72820a1.wiz03.com/share/s/2Ta22x20o4jW2IZNfI1XAGW30wawI70GGkoQ2k40bZ2_CNx5) ##

**EXPLAIN(列)** | **含义**
------ | ------
id | 包含一组数字，表示查询中执行 select 子句或操作表的顺序
   | 当引用其他查询结果做 union 时，该值为 null，且 table 列的值为 union（m,n），意思是把id为m和n的查询结果做 union。
   | id 相同，可以认为是一组，执行顺序由上至下
   | 如果是子查询，id 的序号会递增
   | id 值越大优先级越高，越先被执行