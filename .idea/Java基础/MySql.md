

创建索引：creat index index_name on table_name(column_name)；
删除索引：drop index index_name on table_name;
修改索引：alter table table_name drop index index_name;
查找索引：show index from table_name;
唯一索引：create unique index index_name on table_name(column_name);
主键索引：create primary key index index_name on table_name(column_name);
全文索引：create fulltext index index_name on table_name(column_name);

内联：select * from 表1 表2 where 表1.id=表2.id;
左外联：select * from 表1 left join 表2 on 表1.id=表2.id;
右外联：select * from 表1 right join 表2 on 表1.id=表2.id;

脏读：允许读取未提交的数据
幻读：允许读取其他事务所插入的数据
不可重复读：允许读取其他事务所更新的数据
解决方法：读未提交、读已提交、可重复读（默认）

索引失效：
1.a、b、c组合索引 where a、b索引有效 b、c索引失效（最左原则）
2.where条件中有函数，索引失效
3,字符串不使用引号
4.索引列计算、函数
5.索引列有null值
6.OR语句，如果条件都有索引，索引生效，其中一个没有索引，索引失效

分库分表:
1.垂直分表：把字段拆出来多张表
2.水平分表：数据拆分成多张表
实现技术：
ShardingJDBC：基于AOP实现，对sql进行拦截
Mycat：中间件，性能稍弱，适合小数据量，单代码改动最少
分片配置：schema.xml