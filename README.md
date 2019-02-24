# knowledge


- `@ComponentScan`
> 这个注解完成的是自动扫描的功能，相当于Spring XML配置文件中的：<context:component-scan>，可以使用`basePackages`属性指定要扫描的包，以及扫描的条件。如果不设置的话默认扫描`@ComponentScan`注解所在类的同级类和同级目录下的所有类，所以对于一个Spring Boot项目，一般会把入口类放在顶层目录中，这样就能够保证源码目录下的所有类都能够被扫描到

- `@EnableAutoConfiguration`
>    这个注解告诉Spring Boot 根据添加的jar依赖猜测你想如何配置Spring，例如`spring-boot-starter-web`添加了`Spring MVC` 和`Tomcat` auto Configuration 将假定你在开发一个web应用，并对spring进行相应的设置。
> 借助@Import的帮助，将所有符合自动配置的Bean定义加载到IOC容器内。

```
@SuppressWarnings("deprecation") @Target(ElementType.TYPE) @Retention(RetentionPolicy.RUNTIME) @Documented
@Inherited
@AutoConfigurationPackage @Import(EnableAutoConfigurationImportSelector.class) public @interface EnableAutoConfiguration {
... }
```

- `Import`
> 将Bean 注入spring 容器
```
@Import(EnableAutoConfigurationImportSelector.class)
```



- @SpringbootApplication
> 用于解决根类或配置类注解过多的问题 一个`SpringbootApplication`相当于 `@Configruation` `@EnableAutoConfiguration` `ComponentScan` 并拥有他们的默认属性值


- `Conditional`

> 
```
@ConditionalOnBean（仅仅在当前上下文中存在某个对象时，才会实例化一个Bean）
@ConditionalOnClass（某个class位于类路径上，才会实例化一个Bean）
@ConditionalOnExpression（当表达式为true的时候，才会实例化一个Bean）
@ConditionalOnMissingBean（仅仅在当前上下文中不存在某个对象时，才会实例化一个Bean）
@ConditionalOnMissingClass（某个class类路径上不存在的时候，才会实例化一个Bean）
@ConditionalOnNotWebApplication（不是web应用）

```

