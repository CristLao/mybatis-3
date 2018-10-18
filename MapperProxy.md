MapperProxy
-----------

从下面代码分析sqlSession的执行sql的两种不同方式

```java
Map map = sqlSession.selectOne("org.apache.ibatis.domain.blog.mappers.AuthorMapper.selectAuthorLinkedHashMap");

AuthorMapper authorMapper = sqlSession.getMapper(AuthorMapper.class);
Map map = authorMapper.selectAuthorLinkedHashMap();
```

##### selectOne方式
最终调用org.apache.ibatis.session.defaults.DefaultSqlSession.selectList方法来执行sql

##### 获取Mapper方式
getMapper是用动态代理的方式实现, 本质上和SqlSession的selectOne是一样的  
sqlSession.getMapper -> Configuration.getMapper -> MapperRegistry.getMapper -> mapperProxyFactory.newInstance -> mapperProxy.invoke -> mapperMethod.execute -> sqlSession.selectOne

#### 源码相关
[DefaultSqlSession](src/main/java/org/apache/ibatis/session/defaults/DefaultSqlSession.java) 默认的SqlSession  
[MapperProxyFactory](src/main/java/org/apache/ibatis/binding/MapperProxyFactory.java) MapperProxy的工厂
[MapperProxy](src/main/java/org/apache/ibatis/binding/MapperProxy.java) Mapper的动态代理类
[MapperMethod](src/main/java/org/apache/ibatis/binding/MapperMethod.java) Mapper的执行方法类
[ParamNameResolver](src/main/java/org/apache/ibatis/reflection/ParamNameResolver.java) mapper方法参数解析器


  