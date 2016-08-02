# spring_note
（一）Spring框架——概览
Spring是最流行的企业java应用程序开发框架，全世界数百万的开发者使用spring框架创造高性能的，容易测试的，可重用的代码。

spring框架是一个开源的java平台，最初由Rod Johnson 编写，并在2003年6月在Apache2.0许可发布。

从大小和透明度来说，spring是轻量级的，该框架的基本版本只有大约2MB。

spring框架的核心特性可以用来开发java应用，但是也有在基于Java EE平台之上创建web应用的扩展。Spring框架的目标是使得J2EE的开发更易于使用，并通过基于POJO的编程模型促进良好的编程实践。

使用Spring框架的好处：
Spring能让开发者利用POJOs开发企业级的应用。只是用POJOs的好处是，你不需要类似应用程序服务器的EJB容器产品，你可以值选择一个健壮的servlet容器（如：Tomcat、或其他的一些商业产品）。
Spring是以模块化的方式来组织的。即使有大量的包和类，但是你只需要关心你需要的，而可以忽略其他的。
Spring并没有创造出新的技术，而是正真的利用了一些已经存在的技术，例如几个ORM框架、日志框架、JEE、QuartZ和JDK计时器和其他的视图技术。
测试一个使用Spring编写的代码是很容易的因为环境依赖的代码已经被搬到了这个框架里面。此外，通过使用JavaBean风格的POJOs,使得利用依赖注入的方式注入测试数据变得更加简单。
Spring的web框架是一个设计良好的web MVC 框架，它提供了很多功选择的web框架，像Struts或其他的一些web框架。
Spring提供了一个实用的API，来转化特定于技术的异常（例如：由JDBC、Hibernate或JDO抛出的）到一致的未经检查的异常中。
轻量级的IoC容器往往是轻量级的，尤其是和EJB容器相比较。这个对于在内存和CPU有限的计算机上开发和部署应用是非常有好处的。
Spring提供了一个统一的事物管理接口来按比例缩小到局部事物中（例如使用单一的数据库），或按比例扩大到全局事物中（例如使用JTA）。

依赖注入（DI）：

        Spring最突出的技术就是依赖注入（DI）也叫控制反转。控制反转是一个一般的概念，可以通过不同的方式来表达，而依赖注入仅仅只是其中一个更具人体的解释。

当编写一个复杂的应用程序的时候，应用程序的类应该尽可能的独立于其他的Java类，以此来提高在单元测试中重用和测试这些类独立于其他类的可能性。依赖注入有助于将这些类粘合在一起同时保证每个类的独立性。

        什么是正真的依赖注入？让我们来分开理解这两个词。这里的以来部分转化为两个类的关联。例如：class A 依赖于class B。而注入指的是，class B会通过IoC注入到class A中。

        依赖注入可能发生在传递参数到构造器的方式，或使用setter方法post-construction。

面向切面的编程（AOP）：

       Spring的一个关键的组件就是面向切面的编程（AOP）框架。这个横跨多个应用程序的点的功能被称为横切关注点，这些横切关注点在概念上独立于应用程序的业务逻辑。关于切面这里有很多公共利益方面的例子，包括日志、声明性事物、安全、和缓存等。

       class是OOP中关键的单元模块，而在AOP中模块单元是aspect。DI能够帮助你解耦应用程序中的对象，而AOP能够帮助你解耦有影响的对象的横切关注点。

       Spring框架的AOP模块提供了面向切面的变成实现，能够允许你定义方法拦截器（method-interceptors）和切入点（pointcuts），来干净的解耦代码。

（二）Spring框架——框架结构
Spring可以潜在为你所有的企业应用提供一站式的开发，Spring是模块化的，你可以挑选适合你的模块，而不需要引入其他的模块。在接下来的模块中将给出每个模块的详情。
Spring框架提供了大约20个模块。
核心容器（Core Container）：
Spring的核心容器是由：Core、Beans、Context、和Expression Language几个模块组成：
Core：这个模块提供了框架的基础部分，包含了IoC和依赖注入特性；
Bean：该模块提供了BeanFactory，它是工厂模式的一个复杂实现；
Context：该模块是建立在由Core和Beans两个模块提供的坚实基础上；
SpEL:该模块提供了一个功能强大的在运行时查询和操纵对象图的表达式语言；

数据访问/集成（Data Access/Integration）：
数据访问/集成层是由：JDBC、ORM、OXM、JMS和Transaction几个模块组成：
JDBC:该模块提供了消除编写乏味的与JDBC相关的代码的JDBC抽象层；
ORM:该模块为流行的对象-关系映射APIs提供了集成层，这类APIs包括：JPA、JDO、Hibernate和iBatis；
OXM:该模块为JAXB、Castor、XMLBeans、JiBX和XStream提供了一个支持Object/XML映射的实现；
JMS:该模块包含生产和消费消息的特性；
Transaction：该模块为实现特定接口的类和所有的POJOs支持编程和声明事物管理；

Web：
Web层由：Web、Web-MVC、Web-Socket和Web-Portlet几个模块组成：
Web：该模块提供了基本的面向web（web-oriented）的集成特性，诸如多部件的文件上传（file-upload）功能，利用servlet监听器来初始化IoC容器和面向web的应用上下文。
Web-MVC：该模块包含为web应用的Spring的模型-视图-控制器（MVC）的实现。
Web-Socket:该模块提供了基于WebSocket（WebSocket-based）的支持，在web应用程序中实现客户端和服务器端的双向通信（two-way communication）。
Web-Portlet：该模块提供了用于portlet环境的MVC实现和Web-Servlet模块功能的镜像。

其他模块：
AOP:该模块提供了面向切面的编程实现，允许你定义方法拦截器和横切点来解耦代码。
Aspects：该模块提供了与AspectJ的集成，AspectJ是另一个强大的、成熟的面向切面的编程框架。
Instrumentation：该模块提供了class的工具支持和class加载的实现，被用在某些应用服务器中。
Messaging：该模块提供了对WebSocket子协议STOMP的支持。它也为路由和处理来自WebSocket客户端消息提供了一个注解编程模型。
Test：该模块为使用JUnit和TestNG框架测试Spring组件提供了支持。


（三）Spring框架——IoC容器
Spring容器在其框架的核心。该容器会创建对象，组织对象，配置对象，管理对象从创建到销毁的完整生命周期。Spring容器利用依赖注入来管理组成一个应用的组件。而这些对象就是Spring的Beans。
容器通过读取配置元数据来获取实例化、配置和组装对象的说明。配置元数据可以是XML文件，java注解和java代码。Spring IoC容器通过使用Java POJO类和配置元数据来生成一个完整的可配置和可执行的系统或应用程序。

Spring提供了两个卓越的容器类型：
1、Spring BeanFactory Container（Spring Bean工厂容器）：
这个最简单的容器为DI提供了基本的支持，它被org.springframework.beans.factory.BeanFactory接口所定义。BeanFactory和相关接口（BeanFactoryAware、InitializingBean、DisposableBean），为向后兼容第三方框架到Spring提供了支持。
2、Spring ApplicationContext Container（Spring应用上下文容器）：
这个容器添加了更过特定于企业的功能，如从properties文件中解析文本信息的能力，和传递事件到特定的事件监听器中。这个容器由org.springframework.context.ApplocationContext接口定义。

ApplicationContext容器包含了BeanFactory容器的所有功能，所以ApplicationContext容器是BeanFactory容器的一个特定化。BeanFactory还能被用于轻量级的应用中（如：移动设备或基于applet的应用程序，这些程序的数据量和速度是非常重要的）。

（四）Spring框架——Bean的定义
来自应用程序主干并且被Spring IoC容器管理的对象被称为beans。bean是一个由Spring IoC容器实例化，组织和管理的对象。这些beans是根据为容器提供的配置元数据来创建的，例如配置在XML文件中的<bean/>元数据标签。
bean定义包含有配置元数据提供的信息，容器必需知道如下一些信息：
如何创建bean；
Bean的详细生命周期；
Bean的依赖；
以上所有配置元数据被翻译在一个属性集合中，这个集合组成了每一个bean的定义，一下是每个属性的定义：
class：这个属性指定了创建bean的class；
name：这个属性指定了bean的唯一标识符。在基于XML的配置元数据中，可以使用id和/或name属性来指定bean的标识符；
scope：这个属性制定了所创建的对象的使用范围；
constructor-arg：这个属性被用了注入依赖；
properties：这个属性也是被用来注入依赖；
autowiring mode：这个属性也是被用来注入依赖；
lazy-initialization mode：一个lazy-initialized bean可以告诉IoC容器在第一次被请求创建bean，而不是在容器启动的时候创建；
initialization method：该属性指定bean的所有必需属性被容器设置好之后被回调的方法；
destruction method：该属性指定了容器中的bean在被销毁时被回调的方法。

Spring配置元数据
Spring IoC容器完全脱离了配置元数据被编写的格式。有三个非常重要的方法来为Spring容器提供配置元数据：
基于XML的配置文件；
基于注解的配置；
基于Java的配置；
以下是包含了几个特别属性的基于XML的bean的元数据定义：
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">

   <!-- A simple bean definition -->
   <bean id="..." class="...">
       <!-- collaborators and configuration for this bean go here -->
   </bean>

   <!-- A bean definition with lazy init set on -->
   <bean id="..." class="..." lazy-init="true">
       <!-- collaborators and configuration for this bean go here -->
   </bean>

   <!-- A bean definition with initialization method -->
   <bean id="..." class="..." init-method="...">
       <!-- collaborators and configuration for this bean go here -->
   </bean>

   <!-- A bean definition with destruction method -->
   <bean id="..." class="..." destroy-method="...">
       <!-- collaborators and configuration for this bean go here -->
   </bean>

   <!-- more bean definitions go here -->

</beans>


（五）Spring框架——Bean的作用域
定义bean的时候可以选择性的声明bean的作用域。Spring支持以下五种作用域，其中的三个只有在使用web-aware 应用上下文的时候才能被使用：
singleton：这个作用域指的是在每个Spring IoC容器中以单例的方式创建bean，这也是创建bean的默认方式；
prototype：这个作用域指的是定义任意多个对象实例；
request：这个作用域指的是一个HTTP请求期间，这个只在Spring的web应用上下文中有效；
session：该作用域指的是一个HTTP会话（session）期间，这个只在Spring的web应用上下文中有效；
global-session：这个作用域指的是一个全局的HTTP会话（session）期间，这个只在Spring的web应用上下文中有效。

单例作用域（The singleton scope）：
如果作用域被定义成单例，则Spring IoC容器实际上只会创建一个由该bean定义的对象实例。这个单一的实例被存储在一个类似单例beans的缓存中，所有随后对此的请求都会返回这个缓存中的对象。Spring bean的默认作用域都是单例的。如果你想创建一个指定为单例的bean，你可以在配置文件中指定该bean的作用域属性为singleton，如下：
<!-- A bean definition with singleton scope -->
<bean id="..." class="..." scope="singleton">
    <!-- collaborators and configuration for this bean go here -->
</bean>

原型作用域（The prototype scope）：
如果作用域被定义为prototype，则Spring IoC容器会在每次请求指定bean的时候都生成一个新的对象实例。原则上讲所有的全状态的bean定义为prototype，把所有无状态的bean定义为singleton。例子如下：
<!-- A bean definition with singleton scope -->
<bean id="..." class="..." scope="prototype">
   <!-- collaborators and configuration for this bean go here -->
</bean>

（六）Spring框架——bean的生命周期
Spring bean的生命周期很好理解：当一个bean被初始化的时候，它会被需要执行一些初始化的工作来使它成为可用状态。类似地，当该bean不再被需要且被移出容器的时候，它就会被清除。
在bean初始化和销毁期间，在程序的背后有一系列的活动，接下来会讲到两个重要的生命周期回调方法，分别是bean的初始化喝销毁。

为了定义一个bean的创建和销毁方式，我们通常会在<bean>标签中为其指定init-method和destroy-method参数。init-method属性会在bean初始化的时候被调用。而destroy-method会在bean销毁之前调用。

初始化回调函数（callbacks）：
org.springframework.beans.factory.InitializingBean接口指定了一个唯一的方法：
void afterPropertiesSet() throws Exception;
你可以实现上面的接口和方法，这样初始化工作就会在上面的方法中执行。
在基于XML的元数据配置文件中，你可以使用init-method属性来指定方法的名称，这个方法是没有参数的。例子：
<bean id="exampleBean" class="examples.ExampleBean" init-method="init"/>
下面是类的定义：
public class ExampleBean {
   public void init() {
      // do some initialization work
   }
}

销毁回调函数（Destruction callbacks）：
org.springframework.beans.factory.DisposableBean接口指定了唯一的方法：
void destroy() throws Exception;
你可以实现上面的接口和方法来执行一些对象销毁前的工作。
在基于XML的元数据配置文件中，你可以使用destroy-method属性来指定方法的名称，这个方法是没有参数的。例子：
<bean id="exampleBean" class="examples.ExampleBean" destroy-method="destroy"/>
下面是类的定义：
public class ExampleBean {
   public void destroy() {
      // do some destruction work
   }
}
默认的初始化和销毁方法：
如果你有很多bean的初始化和销毁方法都是共享相同的名称，你不需要为每一个bean指定各自的初始化和销毁方法。框架给我们提供了一个很灵活的配置方式：我们可以在<beans>标签中指定以下两个属性：default-init-method和default-destroy-method，就像下面那样：
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd"
    default-init-method="init" 
    default-destroy-method="destroy">

   <bean id="..." class="...">
       <!-- collaborators and configuration for this bean go here -->
   </bean>

</beans>

（七）Spring框架——Bean Post Processors


（八）Spring框架——Bean Defintion Inheritance

一个bean可以包含很多个配置信息，例如构造器参数，属性值，和特定容器的信息（如：初始化方法、静态工厂名称）等等。
一个child bean的定义可以从parent bean中继承配置数据。child bean可以根据需要覆盖一些属性值，或添加其他新的属性。
Spring bean的继承定义和Java class的继承没有关系，但是继承的原理是相似的。你可以定义一个parent bean作为模板，让其他的child bean来继承它的必需参数配置。

Bean的模板定义：
实际环境中你可以定义一个模板bean来供其他的child bean继承，这样可以省去很多工作。当定义一个模板bean的时候，你可以不用指定class属性，当时需要指定abstract属性值为true，就像下面：
<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">

   <bean id="beanTeamplate" abstract="true">
      <property name="message1" value="Hello World!"/>
      <property name="message2" value="Hello Second World!"/>
      <property name="message3" value="Namaste India!"/>
   </bean>

   <bean id="helloIndia" class="com.tutorialspoint.HelloIndia" parent="beanTeamplate">
      <property name="message1" value="Hello India!"/>
      <property name="message3" value="Namaste India!"/>
   </bean>

</beans>
由于parent bean中没有指定class属性，所以这个bean是不能被实例化的，因此它被明确的标记为abstract。当一个bean被定义成这样的模板bean，那它只能作为被其他child bean继承的模板bean。


（九）Spring框架——依赖注入（DI）
每一个Java应用程序都是一些对象同时一起工作来完成任务的。但是当在写一个复杂的Java应用程序的时候，应该尽可能的减少class之间的依赖，来调高代码的重用性和单元测试。依赖注入就能达到这样的目的。

依赖注入的类型有：基于构造器的注入和基于Setter方法的注入
基于构造器的注入：
该注入方式是容器在调用类的指定参数的构造器的时候完成的，每个参数代表着被依赖的其他类。

基于Setter方法的注入：
该注入方式是容器在调用bean的无参构造器或无参静态工厂方法之后再调用bean的setter方法来初始化引用的类。

可以混合使用两种注入的方式。一个约定俗成的原则是：强制依赖使用有参构造器注入，选择性的依赖使用setter方法注入。
使用DI会使得代码更加的简洁，耦合性更低。对象不需要知道被依赖者，或类的路径，所有的这一切都是Spring框架应该关心的事。


（十）Spring框架——注入内部Beans

（十一）Spring框架——注入集合
Spring提供了如下四种注入集合的配置元素：
<list>:该标签用于注入一列值，且值可以重复；
<set>:该标签用于注入一组值，且值不可以重复；
<map>:该标签用于注入名称和值属于不同类型的名称-值对的集合；
<props>:该标签用于注入名称和值都是String类型的名称-值对的集合；

你可以使用<list>或<set>来注入一个java.util.Collection或一个array（数组）。
你可能会遇到以下两种情况：
直接注入一个集合的值；
注入集合中的bean的引用；

（十二）Beans自动装配（Auto-Wiring）
Spring容器提供了不使用<constructor>和<property>自动装配协作的beans的关系的功能，这样可以帮助你在编写基于Spring的大型应用时减小XML配置的大小。
五种自动注入的模式：
no:这是一种默认的设置方式，即不自动装配属性，而是使用显示的方式来明确指定属性的引用。也就是使用<property>标签来指定需要引用的属性。
byName:通过属性名称来自动装配所需要的属性。如果beans的标签中指定了autowire的属性值为“byName”，会被Spring容器发现。Spring容器会尝试在配置文件中查找一个名称相同的已经注册的beans来自动装配。（我们可以通过设置autowire的值为byName来自动注入需要的属性，但是这种方式需要注意的是，属性的名称必须与已经注册过的bean的名称一致；）
byType:通过属性的数据类型来自动装配所需要的属性。如果beans的标签中指定了autowire的属性值为“byType”，会被Spring容器发现。容器会尝试在配置文件中匹配一个与所需类型一致的已经注册的bean，但是如果存在多个符合要求的bean，就会严重的异常信息抛出。
constructor:这个与byType像是，但是该属性值指定的参数类型是由构造器的参数决定的。如果没有符合要求的bean存在，则会抛出严重的错误。
default:指定该参数值之后，容器会首先使用constructor的方式自动装配，如果不起作用，则会使用byType的方式自动装配。

可以通过byType和constructor的方式来自动装配数组和集合类型。

自动装配的局限性：
如果不经常使用自动装配功能，这种方式可能会给开发人员带来迷惑。虽然，自动装配功能能够显著减少配置属性和构造器参数的工作量，但是我们在使用该功能之前还是要权衡一下该功能的局限性和缺点：
被覆盖的可能性：如果用了自动装配的同时又指定了<constructor-arg>和<property>配置，那么自动装配功能将会被覆盖；
不能自动装配简单的数据类型：不能自动装配简单数据类型，如原生类型（int，float，double，boolean等原生类型），String类型和类。
本质模糊：自动装配功能没有显示指定的方式明确，所以应该竟可能的使用显示指定的方式。

（十三）Spring框架——基于注解的配置
自从Spring2.5开始，使用注解的方式来配置依赖注入成为可能。不同于使用XML的方式来描述bean的装配，我们可以通过在相关的类、方法、变量中使用注解来将bean的配置移到组件类内部。
注解注入将在XML注入之前执行，所以后者将覆盖前者对属性的配置。
注解装配默认不会在Spring容器中打开。所以，在我们确认要使用基于注解的装配之前，我们需要在配置文件中配置注解功能启用。下面是启用注解注入的配置：
<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context-3.0.xsd">

   <context:annotation-config/>
   <!-- bean definitions go here -->

</beans>
配置文件中一旦添加<context:annotation-config/>配置，我们就可以使用注解来自动地将值注入到属性，方法，和构造器中。以下是几个比较重要的注解：
@Required：该注解适用于bean属性以setter方式注入，用该注解修饰的setter方法，在配置文件中必须配置该属性，否则会抛出异常；

@Autowired：该注解适用于bean属性以setter，non-setter，构造器参数方式注入，该注解可以修饰setter方法（修饰setter方法之后，配置文件中可以不用显示的给这个bean配置属性，相应的属性也能被自动注入），也可以直接修饰属性（如果修饰属性，则这个属性可以不用添加setter/getter方法，属性也能自动注入），还可以修饰构造器（修饰构造器之后，构造器的参数可以不用再在配置文件中显示的配置，相应的参数也能被自动注入）；

@Qualifier：该注解与@Autowired注解一起使用，可以用来指定一个将要装配的确切的bean，（例如在配置了两个相同类的bean的时候，这两个注解的同时使用可以明确指定哪一个bean为属性的值，这样就避免了自动注入不明确导致的异常）；

JSR-250注解：Spring支持基于JSR-250的注解，其中包括@Resource，@PostConstruct，@PreDestroy等注解。

（十四）Spring框架——基于Java的配置

（十五）Spring框架——Spring的事件处理
众所周知，Spring的核心是ApplicationContext，它管理者bean的完整生命周期。当bean被加载的时候，ApplicationContext会发布一些事假类型。例如：context在启动的时候ContextStartedEvent事件会被发布，而当context在关闭的时候ContextStoppedEvent事件会被发布。

ApplicationContext中的事件处理是通过ApplicationEvent类和ApplicationListener接口来提供的。所以当bean实现了ApplicationListener接口，那么每次都会有一个ApplicationEvent被发布到ApplicationContext，bean也会被通知。
Spring提供了以下标准事件：
ContextRefreshEvent：这个事件会在ApplicationContext初始化和重新刷新的时候被触发。当然，改时间也会被ConfigurableApplicationContext接口的refresh()方法触发。

ContextStartedEvent：该事件会在使用ConfigurableApplicationContext接口的start()方法启动ApplicationContext的时候被触发。可以在接收到该事件之后关闭数据库连接或重新启动关闭的应用。

ContextStoppedEvent：该事件会在使用ConfigurableApplicationContext接口的stop()方法停用ApplicationContext的时候被触发。可以在接收到该事件之后处理一些必需的任务。

ContextClosedEvent：该事件会在使用ConfigurableApplicationContext接口的close()方法关闭ApplicationContext的时候被触发。关闭的context会接收到该事件来结束生命周期，这种关闭不能被重新启动。

RequestHandledEvent：该事件是特定于web的，会通知所有的bean收到一个HTTP请求。

Spring的事件处理是单线程的，所以当一个事件被触发，在事件被接受者获得之前，进程都会处于阻塞状态。所以，当设计应用时使用到事件处理的时候要特别注意对事件的处理。


Context事件监听：
为了监听context的事件，bean需要实现ApplicationListener接口，该接口只有一个onApplicationEvent()方法。

我们也可以声明个性化的事件，然后以相同的方式来捕获事件。


（十六）Spring框架——AOP
Spring框架的有一个重要组件是面向切面编程（AOP）框架。面向切面编程需要打破程序的逻辑来到一个称为关注点的的独立的部分。这个功能可以跨越程序的多个点，这些点被称为横切关注点，而且这些横切关注点是与应用的业务逻辑无关的。有很多出色的面向切面编程的例子，如日志、审计、声明性事务、安全、和缓存等。
在OOP中关键的模块单元是class（类），而在AOP中关键的模块单元是aspect（面）。依赖注入帮助我们解耦应用中相互关联的对象，而AOP帮助我们解耦互相影响的对象之间的横切关注点。AOP与编程语言中的触发器（trigger）很相似。
Spring AOP模块提供了拦截应用的拦截器，例如，我们可以在某个方法被执行之前或之后来添加额外的功能。

与AOP相关的术语：
以下术语只跟AOP相关，跟Spring没有直接的关系。
Aspect：
Join point：
Advice：
Pointcut：
Introduction：
Target object：
Weaving：

Advice类型：
before：
after：
after-returning：
after-throwing：
around：

个性化的Aspects实现：
Spring支持两种实现个性化切面的方式：@AspectJ注解风格的和schema-based的方式：
基于XML格式的：
如果要使用AOP，你需要在配置文件中添加如下相关的配置信息：
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:aop="http://www.springframework.org/schema/aop"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd 
    http://www.springframework.org/schema/aop 
    http://www.springframework.org/schema/aop/spring-aop-3.0.xsd ">

   <!-- bean definition & AOP specific configuration -->

</beans>
除此之外还需要导入相关依赖的jar包：aspectjrt.jar  aspectjweaver.jar  aspectj.jar  aopalliance.jar。

声明一个aspect：
需要使用<aop:aspect>标签来声明aspect，然后使用ref属性来引用相关的bean，例子：
<aop:config>
   <aop:aspect id="myAspect" ref="aBean">
   ...
   </aop:aspect>
</aop:config>

<bean id="aBean" class="...">
...
</bean>

声明一个pointcut：
切入点有助于确定连接点（方法）执行不同的消息。基于XML格式的配置需要如下定义切入点：
<aop:config>
   <aop:aspect id="myAspect" ref="aBean">

   <aop:pointcut id="businessService"
      expression="execution(* com.xyz.myapp.service.*.*(..))"/>
   ...
   </aop:aspect>
</aop:config>

<bean id="aBean" class="...">
...
</bean>

声明advices
可以在<aop:aspect>中使用<aop:{ADVICE NAME}>声明五个消息中的任意一个或多个：
<aop:config>
   <aop:aspect id="myAspect" ref="aBean">
      <aop:pointcut id="businessService"
         expression="execution(* com.xyz.myapp.service.*.*(..))"/>

      <!-- a before advice definition -->
      <aop:before pointcut-ref="businessService" 
         method="doRequiredTask"/>

      <!-- an after advice definition -->
      <aop:after pointcut-ref="businessService" 
         method="doRequiredTask"/>

      <!-- an after-returning advice definition -->
      <!--The doRequiredTask method must have parameter named retVal -->
      <aop:after-returning pointcut-ref="businessService"
         returning="retVal"
         method="doRequiredTask"/>

      <!-- an after-throwing advice definition -->
      <!--The doRequiredTask method must have parameter named ex -->
      <aop:after-throwing pointcut-ref="businessService"
         throwing="ex"
         method="doRequiredTask"/>

      <!-- an around advice definition -->
      <aop:around pointcut-ref="businessService" 
         method="doRequiredTask"/>
   ...
   </aop:aspect>
</aop:config>

<bean id="aBean" class="...">
...
</bean>
可以使用相同的或不用的方法来处理这些advices。这些方法会作为aspect模块的一部分被定义。


基于@AspectJ注解的：



































