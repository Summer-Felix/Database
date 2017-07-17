# [优化](https://github.com/Summer-Felix/Database/blob/master/MySQL/优化.md) #

## [Explain](http://b72820a1.wiz03.com/share/s/2Ta22x20o4jW2IZNfI1XAGW30wawI70GGkoQ2k40bZ2_CNx5) ##

| ***EXPLAIN(列)*** | ***含义*** |
| :------ | :------ |
| id | 包含一组数字，表示查询中执行 select 子句或操作表的顺序 </br> 当引用其他查询结果做 union 时，该值为 null，且 table 列的值为 union（m,n），意思是把id为m和n的查询结果做 union。 </br> id 相同，可以认为是一组，执行顺序由上至下 </br> 如果是子查询，id 的序号会递增 </br> id 值越大优先级越高，越先被执行 |
| select_type | 表示查询中每个 select 子句的类型（简单 、复杂） </br> simple (简单)       : 表示此查询不包含 UNION 查询或 子查询 </br> primary (主)        : 查询中若包含复杂的子部分，则最外层查询为 primary </br> subquery (子查询)   : 在 SELECT 或 WHERE 列表中包含了子查询，该子查询被标记为 SUBQUERY </br> union (联合)        : 若第二个select出现在union之后，则被标记为union，如果有多个union，则除第一个select之外，后续的都是union。 </br> dependent union    : 在union中的第二个及以后的查询语句，依赖于外层查询。 </br> union result       : union的结果，id列为null，table列显示了是由哪几个查询的结果做的union。 </br> dependent query    ：子查询中的第一个查询，依赖于外部查询。 </br> derived            ：在FROM列表中包含的子查询被标记为DERIVED（衍生）。若UNION包含在 FROM子句的子查询中，外层SELECT将被标记为DERIVED </br> materialized       ：物化子查询 </br> dependent subquery : 子查询中的第一个 SELECT, 取决于外面的查询. 即子查询依赖于外层查询的结果. </br> uncacheable union  ：该查询是union查询中的第二个及以后的查询语句，且整个union查询语句是一个uncacheable subquery。 </br>  </br> dependent subquery评估和uncacheable subquery评估不同。 </br> dependent subquery对于外部查询中的不同的值只计算一次。 </br> 而uncacheable subquery对于外部查询中的每一行都重新评估一次。 |
| table | table 查询结果出自哪张表。可以是具体的表名，也可以是以下的值： </br> union M，N：id为M和N的查询结果做union </br> derivedN ：参考id为N的查询的衍生查询 </br> subqueryN ：参考id为N的物化子查询 |