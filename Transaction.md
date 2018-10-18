Transaction
-----------

Mybatis的事务类型有两种
* JDBC事务模型：[JdbcTransaction](src/main/java/org/apache/ibatis/transaction/jdbc/JdbcTransaction.java)：直接使用JDBC来管理事务的各个环节：提交、回滚、关闭等操作  
* MANAGED事务模型：[ManagedTransaction](src/main/java/org/apache/ibatis/transaction/managed/ManagedTransaction.java)：将事务管理交给容器管理，Mybatis不实现事务功能  

| 事务隔离级别 | 说明 |
| :------: | :------: |
TRANSACTION_NONE | 说明不支持事务。
TRANSACTION_READ_UNCOMMITTED | 说明在提交前一个事务可以看到另一个事务的变化。允许读脏，不可重复读，幻读。
TRANSACTION_READ_COMMITTED | 说明读取未提交的数据是不允许的。这个级别仍然允许不可重复的读和幻读产生。
TRANSACTION_REPEATABLE_READ | 说明事务保证能够再次读取相同的数据而不会失败，但幻读仍然会出现。
TRANSACTION_SERIALIZABLE | 是最高的事务级别，它防止脏读、不可重复的读和幻读。 
