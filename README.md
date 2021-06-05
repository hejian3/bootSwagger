#### Swagger 3.0与Sprinngboot2.3.11集成

##### 环境

| 组件       | 版本           |
| ---------- | -------------- |
| JDK        | 8              |
| Springboot | 2.3.11.RELEASE |
| swagger    | 3.0.0          |

##### 引入swagger

```xml
<dependency>
       <groupId>io.springfox</groupId>
       <artifactId>springfox-boot-starter</artifactId>
       <version>3.0.0</version>
</dependency>
```

##### 注意事项

不要引入spring-context-indexer,官方已认定为BUG

[Springfox swagger2 @Component does not get indexed by Spring Framework 5 spring-context-indexer]: https://github.com/springfox/springfox/issues/2451

```xml
 <dependency>
         <groupId>org.springframework</groupId>
         <artifactId>spring-context-indexer</artifactId>
 </dependency>
```

![img](https://img2018.cnblogs.com/blog/1642600/201903/1642600-20190325152111154-792892722.png)

