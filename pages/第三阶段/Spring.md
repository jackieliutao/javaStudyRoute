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
- - - Spring提供了面向切面编程的丰富支持，允许通过分离应用的业务逻辑与系统级服务（例如审计（auditing）和事务（transaction）管理）进行[<font color="blue">内聚性</font>](https://baike.baidu.com/item/%E5%86%85%E8%81%9A%E6%80%A7/4973441?fr=aladdin)的开发。应用对象只实现它们应该做的——完成业务逻辑——仅此而已。它们并不负责（甚至是意识）其它的系统级关注点，例如日志或事务支持。

- - - [<font color="blue">高内聚低耦合</font>](https://baike.baidu.com/item/%E9%AB%98%E5%86%85%E8%81%9A%E4%BD%8E%E8%80%A6%E5%90%88/5227009)
- - D：容器
- - - Spring包含并管理应用对象的配置和生命周期，在这个意义上它是一种容器，你可以配置你的每个bean如何被创建----基于一个可配置原型，你的bean可以创建一个单独的实例或者每次需要时都生成一个新的实例----以及它们是如何相互关联的。
- - E：框架
- - - Spring可以将简单的组件配置、组合成为复杂的应用。在Spring中，应用对象被声明式地组合，典型地是在一个XML文件里。Spring也提供了很多基础功能（事务管理、持久化框架集成等等），将应用逻辑的开发留给了你。
- <h4 id="modules" style="color:red;font-weight:bold">（二）常用模块</h4>
- - A：核心容器
- - - 核心容器提供Spring框架的基本功能。核心容器的主要组件是BeanFactory，它是工厂模式的实现。BeanFactory使用控制反转（IOC）模式将应用程序的配置和依赖性规范与实际的应用程序代码分开。
- - B：Spring上下文
- - - Spring上下文是一个配置文件，向Spring框架提供上下文信息。Spring上下文包括企业服务，例如JNDI、EJB、电子邮件、国际化、校验和调度功能。
- - C：Spring AOP
- - - 通过配置管理特性，Spring AOP模块直接将面向切面的编程功能集成到了Spring框架中。可以将一些通用任务，如安全、事务、日志等集中进行管理，提高了复用性和管理的便捷性。
- - D：Spring DAO
- - - 为JDBC DAO抽象层提供了有意义的异常层次结构，可用该结构来管理异常处理和不同数据库供应商抛出的错误信息，异常层次结构简化了错误处理，并且极大地降低了需要编写的异常代码数量（例如打开和关闭链接）。Spring DAO的面向JDBC的异常遵从通用的DAO异常层次结构。
- - E：Spring ORM
- - - Spring框架插入了若干个ORM框架，从而提供了ORM的对象关系工具，其中包括JDO、Hibernate和iBatis SQL Map。所有这些都遵从Spring的通用事务和DAO异常层次结构。
- - F：Spring Web模块
- - - Web上下文模块建立在应用程序上下文模块之上，为基于Web的应用程序提供了上下文。所以，Spring框架支持与Jakarta Struts的集成。Web模块还简化了处理多部分请求以及将请求参数绑定到域对象的工作。
- - G：Spring MVC框架
- - - MVC框架是一个全功能的构建Web应用程序的MVC实现。通过策略接口，MVC框架变成为高度可配置的，MVC容纳了大量视图技术，其中包括JSP、Velocity、Tiles、iText和POI。
- <h4 id="jar" style="color:red;font-weight:bold">（三）主要JAR包</h4>
- - - org.springframework.core——Spring的核心工具包，其他包依赖此包
- - - org.springframework.beans——所有应用都用到，包含访问配置文件，创建和管理bean等。
- - - org.springframework.aop——Spring的面向切面编程，提供AOP（面向切面编程）的实现
- - - org.springframework.context——提供在基础IOC功能上的扩展服务，此外还提供许多企业级服务的支持，有邮件服务、任务调度、JNDI、EJB集成、远程访问、缓存以及多种视图层框架的支持。
- - - org.springframework.web.mvc——包含SpringMVC应用开发时所需的核心类
- - - org.springframework.transaction——为JDBC、hibernate、JDO、JPA提供一致的声明式和编程式事务
- - - org.springframework.web——包含Web应用开发时，用到Spring框架时所需的核心类
- - - org.springframework.aspects——Spring提供的对AspectJ框架的整合
- - - org.springframework.test——对JUNIT等测试框架的简单封装
- - - org.springframework.asm——spring3.0开始提供自己独立的asm jar包
- - - org.springframework.context.support——Spring context的扩展支持，用于MVC方面
- - - org.springframework.expression——Spring表达式语言
org.springframework.instrument.tomcat——Spring对tomcat连接池的集成
- - - org.springframework.instrument——Spring对服务器的代理接口
- - - org.springframework.jdbc——对JDBC的简单封装
- - - org.springframework.jms——为简化jms api的使用而做的简单封装
- - - org.springframework.orm——整合第三方的orm实现，如hibernate、ibatis、jdo、jpa等
- - - org.springframework.oxm——Spring对object/xml映射的支持，可以让JAVA与XML来回切换
- - - org.springframework.web.portlet——Spring MVC的增强
- - - org.springframework.web.servlet——对J2EE6.0 servlet3.0的支持
- - - org.springframework.web.struts——整合对struts框架的支持，更方便更容易的集成struts框架
- <h4 id="annotation" style="color:red;font-weight:bold">（四）常用注解</h4>
- - - @Controller
- - - - 用于标注控制层组件
- - - - @Controller用于标记在一个类上，使用它标记的类就是一个spring-coreMVC Controller对象
- - - - 分发处理器将会扫描使用了该注解的类的方法，并检测该方法是否使用了@RequestMapping注解
- - - - 可以把request请求Header部分的值绑定到方法的参数上
- - - @RestController
- - - - 相当于@Controller和@responseBody的组合效果
- - - @Component
- - - - 泛指组件，当组件不好归类的时候，我们可以使用这个注解进行标注
- - - @Repository
- - - - 用于标注dao层，在daoImpl类上面注解
- - - @Service
- - - - 用于标注业务层组件
- - - @ResponseBody
- - - - 异步请求
- - - - 该注解用于将Controller的方法返回的对象，通过适当的HttpMessageConverter转换为指定格式后，写入到Response对象的body数据区
- - - - 返回的数据不是html标签，而是其他某种格式的数据时（如json、xml）使用
- - - @RequestMapping
- - - - 一个用来处理请求地址映射的注解，可用于类或方法上。用于类上，表示类中的所有响应请求的方法都是以该地址作为父路径。
- - - @Autowired
- - - - 它可以对成员变量、方法及构造函数进行标注，完成自动装配工作。通过@Autowired的使用来消除set、get方法。
- - - @PathVariable
- - - - 用于将请求URL中的模板映射到功能处理方法的参数上，即取出uri模板中的变量作为参数
- - - @requestParam
- - - - 主要用于在SpringMVC后台控制层获取参数，类似一种是request.getParameter("name")
- - - @RequestHeader
- - - - 可以把Request请求header部分的值绑定到方法的参数上
- - - @ModelAttribute
- - - - 该Controller的所有方法在调用前，先执行@ModelAttribute方法，可用于注解方法和方法参数中，可以把这个@ModelAttribute特性应用在BaseController当中，所有的Controller继承BaseController，即可实现在调用Controller时，先执行@ModelAttribute方法。
- - - @SessionAttributes
- - - - 即将值放到session作用域中，写在class上面
- - - @Valid
- - - - 实体数据校验，可以结合hibernate validator一起使用
- - - @CookieValue
- - - - 用来获取Cookie中的值
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
