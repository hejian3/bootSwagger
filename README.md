#### Swagger 3.0与Sprinngboot2.3.11集成

##### 环境

| 组件       | 版本           |
| ---------- | -------------- |
| JDK        | 8              |
| Springboot | 2.3.11.RELEASE |
| swagger    | 3.0.0          |
| knife4j    | 3.0.2          |

##### 引入swagger

```xml
<dependency>
       <groupId>io.springfox</groupId>
       <artifactId>springfox-boot-starter</artifactId>
       <version>3.0.0</version>
</dependency>
```

访问文档：http://localhost:8080/swagger-ui/

##### 禁用swagger

```yaml
springfox:
  documentation:
    swagger-ui:
      enabled: true
```



##### 引入knife4j（可以生成离线文档）

```xml
<dependency>
    <groupId>com.github.xiaoymin</groupId>
    <artifactId>knife4j-spring-boot-starter</artifactId>
    <version>3.0.2</version>
</dependency>
```

访问文档：http://localhost:8080/doc.htm

##### 注意事项

不要引入spring-context-indexer,官方已认定为BUG

[Springfox swagger2 @Component does not get indexed by Spring Framework 5 spring-context-indexer]: https://github.com/springfox/springfox/issues/2451

```xml
 <dependency>
         <groupId>org.springframework</groupId>
         <artifactId>spring-context-indexer</artifactId>
 </dependency>
```

##### spring-context-indexer简介

项目编译完成时就会就会生成 `META-INF/spring.components` 文件到 jar 包中，从运行时扫描改成编译期间，大大提高了启动速度，类似的有 `Lombok`， `spring-boot-configuration-processor` 。
