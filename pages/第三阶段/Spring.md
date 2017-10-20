---
layout: post
title:  "Spring"
date:   2017-10-19
comments: true
---

* [1、Spring入门](#spring)
* * [1.1、Spring特征](#feature)
* * [1.2、常用模块](#modules)
* * [1.3、主要jar包](#jar)
* * [1.4、常用注解](#annotation)
* * [1.5、装配注解比较](#compareAnnos)
* * [1.6、第三框架集成](#frame)
* [2、反转控制IOC](#ioc)
* [3、依赖注入DI](#DI)
* [4、Bean配置与原理](#bean)
* [5、注解开发](#annotation)
* [6、面向切面编程AOP](#aop)
* [7、事务管理](#transactionManager)


<h3 id="spring">一：Spring入门</h3>

- <h4 id="feature" style="color:red;font-weight:bold">（一）Spring特征</h4>
- - A:轻量
- - - 从大小与开销两方面而言，Spring都是轻量的。完整的spring-core框架可以在一个大小只有1M多的JAR文件里发布，并且Spring所需的处理开销也是微不足道的。
- - - 此外，Spring是非侵入式的;典型的，Spring应用中的对象不依赖于Spring的特定类。
- - B：控制反转
- - - Spring通过一种称作控制反转（IoC）的技术促进了松耦合。当应用了IoC，一个对象依赖的其它对象会通过被动的方式传递进来，而不是这个对象自己创建或者查找依赖对象。你可以认为IoC与JNDI相反——不是对象从容器中查找依赖，而是容器在对象初始化时不等对象请求就主动将依赖传递给它。
- - C：面向切面
- - - Spring提供了面向切面编程的丰富支持，允许通过分离应用的业务逻辑与系统级服务（例如审计（auditing）和事务（transaction）管理）进行[内聚性](https://baike.baidu.com/item/%E5%86%85%E8%81%9A%E6%80%A7/4973441?fr=aladdin)的开发。应用对象只实现它们应该做的——完成业务逻辑——仅此而已。它们并不负责（甚至是意识）其它的系统级关注点，例如日志或事务支持。

- - - <font color="blue">[高内聚低耦合](https://baike.baidu.com/item/%E9%AB%98%E5%86%85%E8%81%9A%E4%BD%8E%E8%80%A6%E5%90%88/5227009)</font>
- - D：容器
- - - Spring包含并管理应用对象的配置和生命周期，在这个意义上它是一种容器，你可以配置你的每个bean如何被创建----基于一个可配置原型，你的bean可以创建一个单独的实例或者每次需要时都生成一个新的实例----以及它们是如何相互关联的。
- - E：框架
- - - Spring可以将简单的组件配置、组合成为复杂的应用。在Spring中，应用对象被声明式地组合，典型地是在一个XML文件里。Spring也提供了很多基础功能（事务管理、持久化框架集成等等），将应用逻辑的开发留给了你。
- <h4 id="modules" style="color:red;font-weight:bold">（二）常用模块</h4>
- - A：核心容器
- - B：Spring上下文
- - C：Spring AOP
- - D：Spring DAO
- - E：Spring ORM
- - F：Spring Web模块
- - G：Spring MVC框架
- <h4 id="jar" style="color:red;font-weight:bold">（三）主要JAR包</h4>
- <h4 id="annotation" style="color:red;font-weight:bold">（四）常用注解</h4>
- <h4 id="compareAnnos" style="color:red;font-weight:bold">（五）装配注解比较</h4>
- - A：包区别
- - B：@Autowired和@Inject
- - C：@Resource
- <h4 id="frame" style="color:red;font-weight:bold">（六）第三框架集成</h4>
- - A：权限
- - B：缓存
- - C：持久层框架
- - D：定时任务
- - E：校验框架

<h3 id="ioc">二：反转控制IOC</h3>
<h3 id="DI">三：依赖注入DI</h3>
<h3 id="bean">四：Bean配置与原理</h3>
<h3 id="annotation">五：注解开发</h3>
<h3 id="aop">六：面向切面编程AOP</h3>
<h3 id="transactionManager">七：事务管理</h3>
