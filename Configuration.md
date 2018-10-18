Configuration
-------------

Configuration是MyBatis的配置类，读取xml配置是Configuration的重点
#### 源码相关
[Configuration](src/main/java/org/apache/ibatis/session/Configuration.java) 配置类  
[MapperRegistry](src/main/java/org/apache/ibatis/binding/MapperRegistry.java) mapper注册中心  
[InterceptorChain](src/main/java/org/apache/ibatis/plugin/InterceptorChain.java) 插件链  
[TypeHandlerRegistry](src/main/java/org/apache/ibatis/type/TypeHandlerRegistry.java) 类型转换注册  
[XMLConfigBuilder](src/main/java/org/apache/ibatis/builder/xml/XMLConfigBuilder.java) 解析xml配置，用于生成Configuration实例  








