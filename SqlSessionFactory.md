SqlSessionFactory
-----------------

从SqlSessionFactory和Configuration的创建过程中可以看出它们都使用了建造者模式  
#### 源码相关
[SqlSessionFactoryBuilder](src/main/java/org/apache/ibatis/session/SqlSessionFactoryBuilder.java) 用来创建SqlSessionFactory实例  
[XMLConfigBuilder](src/main/java/org/apache/ibatis/builder/xml/XMLConfigBuilder.java) 读取配置文件返回configuration  
[DefaultSqlSessionFactory](src/main/java/org/apache/ibatis/session/defaults/DefaultSqlSessionFactory.java) 默认创建的SqlSessionFactory  

