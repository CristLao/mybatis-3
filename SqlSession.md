SqlSession
-----------------

#### 源码相关
[SqlSessionFactoryBuilder](src/main/java/org/apache/ibatis/session/SqlSessionFactoryBuilder.java) 用来创建SqlSessionFactory实例  
[XMLConfigBuilder](src/main/java/org/apache/ibatis/builder/xml/XMLConfigBuilder.java) 读取配置文件返回configuration  
[DefaultSqlSessionFactory](src/main/java/org/apache/ibatis/session/defaults/DefaultSqlSessionFactory.java) 默认创建的SqlSessionFactory  
[DefaultSqlSession](src/main/java/org/apache/ibatis/session/defaults/DefaultSqlSession.java) 默认的SqlSession  

SqlSession的实例不是线程安全的，是不能被共享的，官方推荐SqlSession的生命周期是在Method级别的，值得一提的是在Spring和MyBatis集成时, Mybatis提供了一个SqlSessionTemplate的类, 每次调用Mapper里面的方法实际上都是利用了该类的内部类SqlSessionInterceptor动态生成一个SqlSession来执行, 虽然MyBatis集成到Spring中时mapper不是文档推荐的method级别的，但是实际上和动态生成的SqlSession的生命周期的时一样的。
