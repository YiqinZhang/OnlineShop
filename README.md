# OnlineShop

Spring and Hibernate-based E-commence web application allows customers to sign in, register accounts, choose products, and check out.



## Architecture

[![img](https://github.com/YiqinZhang/OnlineShop/raw/master/img/01.png)](https://github.com/YiqinZhang/OnlineShop/blob/master/img/01.png)

## Spring MVC

Spring MVC provides a framework to support DispatcherServlet, HandlerMapping, Controller, ModelandView, and ViewResolver. Utilized Spring-AOP (Aspect Oriented Programming) and Inversion of Control & Dependency Injection. The spring framework initializes all the classes needed to run the application through annotation-based and java-based configurations. 

[![img](https://github.com/YiqinZhang/OnlineShop/raw/master/img/03.png)](https://github.com/YiqinZhang/OnlineShop/blob/master/img/03.png)

**DispatcherServlet(前端控制器)**: handles all the HTTP requests and responses.

**HandlerMapping(映射处理器)**: Map a request to a handler that helps the DispatcherServlet to invoke, for example, a controller can be a handler.

**Controller(处理器)**: A component to express request mappings, request input.

**ModelAndView(模型和视图)**: Represents a model and view returned by a handler, to be resolved by the DispatcherServlet.

**ViewResolver(视图解析器)**: a mapping between view names and actual views.

1.首先用户发送请求-->前端控制器(DispatcherServlet), 前端控制器根据请求信息(如URL)来决定选择哪一个控制器进行处理并把请求委托给它.

2.控制器(controller)接收到请求后, 首先它会在自己内部寻找一个合适的方法来处理请求(用@RequestMapping将方法映射到请求上), 然后传入收到的请求并且调用业务对象进行处理; 处理完毕后返回一个ModelAndView(模型数据和逻辑视图名). '

3.前端控制器根据返回的逻辑视图名, 选择相应的视图进行渲染, 并把模型数据传入以便视图渲染.

4.前端控制器再次收回控制权, 将响应返回给用户.



## Spring Security

[![img](https://github.com/YiqinZhang/OnlineShop/raw/master/img/04.png)](https://github.com/YiqinZhang/OnlineShop/blob/master/img/04.png)

Spring Security provides security services for Java EE-based enterprise software applications.

**Authentication**

The process of checking credentials and making sure the current logged user is who they claim to be. Used Spring Security to implement OAuth2 based authentication and improved reliability of ordering and checking

**Authorization**

The process of deciding whether a current logged user is allowed to perform an action within your application.

## Hibernate

Hibernate is an object-relational mapping tool for the Java programming language which implements the Java Persistence API. Hibernate's primary feature is mapping from Java classes to database tables, and mapping from Java data types to SQL data types. Hibernate provides data manipulation facilities. Utilized Hibernate to map object-oriented domain models to relational database tables.

**Important interfaces of Hibernate framework**

`SessionFactory`: SessionFactory is an immutable thread-safe cache of compiled mappings for a single database. Initialize the sessionFactory once and then reuse it. SessionFactory instance is used to get the Session objects for database operations.

`Session`: Session object is the interface between java application code and hibernate framework and provides methods for CRUD operations.

`Transaction`: Transaction is an object used by the application to specify atomic units of work.

[![img](https://github.com/YiqinZhang/OnlineShop/raw/master/img/02.png)](https://github.com/YiqinZhang/OnlineShop/blob/master/img/02.png)

### Spring Web Flow

A flow encapsulates a sequence of steps that guides users through the execution of some business logic, such as checkout. In Spring Web Flow, a flow consists of a series of steps called "states". Entering a state typically results in a view being displayed to users so that they can interact with the system or some backend logic is performed. The result of one state can trigger transitions to other states.

- States：states are points in a flow where something happens.
- Transitions：transitions connect the states within a flow.
- Flow data：the current condition of the flow.



### Microservice

The microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API. These services are built around business capabilities and independently deployable by fully automated deployment machinery.

一系列独立的服务共同组成系统

单独部署, 跑在自己的进程里

每个服务为独立的业务开发



##### API Gateway(Spring cloud Gateway)

[![img](https://github.com/YiqinZhang/OnlineShop/raw/master/img/05.png)](https://github.com/YiqinZhang/OnlineShop/blob/master/img/05.png)

Communication in microservices: Synchronous: RESTful, RPC(Dubbo)

[![img](https://github.com/YiqinZhang/OnlineShop/raw/master/img/07.png)](https://github.com/YiqinZhang/OnlineShop/blob/master/img/07.png)
