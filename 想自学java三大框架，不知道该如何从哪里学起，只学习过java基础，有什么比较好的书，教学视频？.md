



**作为一名用Java十几年的程序员，我来告诉你学Java框架事半功倍的经验！**

常说的三大框架是指SSM，我再补充一个框架：Netty（网络框架）。于是最常用的框架就是：

* Spring
* Spring MVC
* Spring Boot
* Mybatis
* Netty

一眼就能看出来，这些框架中Spring的最多。我先说说怎么学Sping。

## 一、学Spring

Spring、SpringMVC、SpringBoot、SpringCloud……Spring 发展到现在，它已经成为了一套完整的体系了，而且 Spring 迭代非常快，几乎每年都会出现大的变化。

虽然 Spring 变化确实很快，但是，它有几个地方，是这么多年几乎没发生过什么变化的。

没有什么变化的第一部分，就是 Spring 的设计思路。Spring 的设计思路，**永远都是作为 Bean 的容器，去管理好 Bean** ，这是它永恒不变的地方。

没有什么变化的第二部分，就是 Spring 的内核。Spring 的 ApplicationContext 等核心 API 是没有什么大的变化的。

所以，咱们就应该先从 Spring 这些不变的核心先入手。**掌握住 Spring 的思想，Spring 的内核，哪怕 Spring 本身再变化，对咱们来说，也只是一种外在的 API 变化而已。**

要达到这个目的，我会推荐大家看一本很老的书《Spring揭秘》（豆瓣 9.1分）。

![[v2-5786bd97feb05dc0a41c67920de0713e_720w.jpg]]
()

虽然这本书主要是以 Spring3 的讲解为基础，但是，这本书对于 Spring 的编程思想讲的极为透彻，是有关 Spring 的书中，难得一见的好书。入门 Spring，这是我推荐的第一本书。

理解了 Spring 的编程思想不够，我们需要利用这些思想，去实践演练，加强我们对 Spring 的理解。

这时候，就得有本书，能真正的带我们实战下Spring的各个组件——《精通Spring 4.x》（豆瓣 8.5 分）。

![[v2-b6cd4c0e9d190e8f484e6dcad4a054c4_720w.jpg]]
()

现在 Spring 5 在逐渐进入主流，但是 Spring 5 也只是在 Spring 4 的基础上增加了一些新特性。

理解了 Spring 的理念，用很多代码练习练习实践之后，我们就只需要知道 Spring 5 的一些特性就能跟上 Spring 发展的步伐了。可以看下《Spring 5 开发大全》，这本书对 Spring 5 的新特性介绍很全。

关于 SpringBoot，由于它的易用性，它已经迈入主流。不过 SpringBoot 也只是以 Spring 为内核的一套应用框架而已。找本书，学习它是如何通过添加一些模块和功能，去降低大家使用 Spring 的门槛的，也就够了。可以读下《Spring Boot 2实战之旅》。

**在这里一份我整理的“豆瓣高分计算机书单”，除了有上面几本Spring书，还有其他编程、Java经典书籍。几乎都是8分以上的好书。**

![[v2-78796f00aa9b785bf6466d69f1a78bcf_720w.jpg]]
()

![[v2-b8a3554e472d02a8d7e399075e1d092c_720w.jpg]]
()

**书单详细内容和pdf免费下载方式看这个（有需要下载的尽快了）**

接下来说说学Spring的具体步骤：

### 第一步、找到最核心的内容

学好 Spring 的第一步就是：从以上书籍或者其他书籍、资料文档中，找到 Spring 庞大的知识体系中**最核心最重要最值得学习**的知识点，抽取出来形成学习清单。

例如，我提取的核心知识点是：

**1. Spring 到底是如何管理对象的**

我们使用 Spring 的时候，大部分其实都是在使用 Spring 的核心容器功能。

Spring 的容器功能就是通过 BeanFactory 和对应的子类各种 xxxContext 去存储管理对象。

这个知识点是 Spring 发展至今一直没有变化的核心知识。

**2. Spring 注入对象的方式和对应原理**

当 Spring 成为对象容器后，它本身最重要的目的就是要去对系统中各种类进行对象注入。而工作中最常见的问题，就是 Spring 注入对象的各类问题。

也因此，广泛了解 Spring 注入对象的各类方式，从而能更加灵活地运用 Spring，深入理解注入对象的对应原理，从而能顺利无误地使用 Spring，就是我们深入学习 Spring 的重要目标。

**3. Spring 是如何管理对象之间的依赖关系的**

除了使用完整对象的注入以外，工作中，我们还需要考虑对被注入对象属性的动态修改，可能还想要动态地注册新的 Bean 对象等等。

而要做到这些，我们就必须去了解 Spring 是如何管理对象之间的依赖关系的。

**4. AOP 的实现原理以及对其的内部使用**

AOP 在 Spring 项目中被广泛用于权限、错误处理以及日志追踪等关键场景。

尤为重要的是，Spring 项目中的所有相关数据库事务，也都是通过 AOP 来管理和传播的。

所以对 AOP 的学习也颇为重要。

**5. Spring 的扩展点有哪些以及如何做**

很多时候，我们需要把公司的一些内部框架和系统嫁接到 Spring 中。为了减少开发成本，就要自定义一套完整的 Spring 扩展，比如：自定义注解、自定义配置类等。

想做到这些，就必须知道 Spring 有哪些扩展点，可以做什么扩展以及怎么做扩展。

**6. Spring MVC 的体系和重要类的作用**

哪怕现在大家都使用 SpringBoot 了，但是，只要我们在用 SpringBoot 的 Web 功能，其实就是在和 SpringBoot 背后内置的 Spring MVC 打交道。

Spring MVC 本身有一套复杂的体系，从请求到响应，有一套完整复杂的流程。只有了解这些流程和 Spring MVC 的体系，我们才能顺畅使用 Spring MVC，去解决 Web 项目中各种看起来很奇怪的问题以及作出新的扩展功能，比如，项目中的国际化出现的各种乱码问题，统一错误处理问题等。

**7. Spring Boot 是如何自动配置好类的**

Spring Boot 本身就是以 Spring 作为对象容器，以 Spring MVC 实现 Web 功能的一套缝合框架。学习了 Spring 和 Spring MVC 之后，我们就理解了 Spring Boot 绝大部分功能。

但是，Spring Boot 是如何把 Spring 中的各个组件缝合在一起的？其中重要的思想就是自动配置。

所以，学习了 Spring Boot 的自动配置，我们就能从头到尾完整的了解 Spring Boot 的整体体系结构和相关对象管理流程。

提取出学习内容后，强烈建议大家学习中记下我们的笔记和思考，并定期复习。

**说明一下**：除了上述知识点，有一些知识点我没说，例如：Spring MVC 中我并没有提及拦截器，也没有提及Spring Boot 中常用的各种注解。

之所以没说，是因为这些内容，是 Spring 必须内容，你绕不开他们。而我提及的这些，则是 Spring 学习中，大家经常不知所措，也不知道要学的那些重要内容。

### 第二步、做一些实际练习

学习上面知识点的过程中，应该结合实际的一些场景，再做一些练习。这里我对应每个知识点给出一些练习建议，大家可以照着做一下。

* 写一个使用 AnnotationConfigApplicationContext 去获取对象的测试用例：写这个测试用例的目的是，让我们能更加清楚地理解 Spring 是如何用容器管理对象的。
* 写一个能使用 FactoryBean 去产生一个对象的测试用例：目的是想让大家明白，Spring 创建对象并不止是一种方式，大家可以多了解下其他的创建对象的方式，同时也多多思考。
* 写一个能在 Spring 中动态新增对象的测试用例。
* 写一个能在 Spring 中动态删除对象的测试用例。
* 写一个能在 Spring 中动态修改Bean属性的测试用例。

以上的测试用例，我建议大家使用 Spring 中的相关 BeanFactoryPostProcessor、BeanDefinitionRegistryPostProcessor 等内部对象来实现，而不是简单的从容器中获取 Bean，然后采用反射去修改对应的值或者对象。

我们写这几个测试用例的目的是为了让大家对 Spring 是如何管理对象以及对象依赖关系的，有更进一步的体会。

* 写一个能观察 Bean 的生命周期的测试用例：目的是能让大家进一步了解 Spring 对象的管理。这个测试用例尽量写全，生命周期观察的越细致越好。比如，我们不仅要实现 init 和 destroy 方法，还要采用 BeanNameAware、InitializingBean 等方式，去尽量把完整的 Bean 生命周期展示出来。
* 写一个或者几个能用 AOP 功能的测试用例：加深对 Spring AOP 的理解的，最好是把 AOP 中的前置通知、[后置通知](https://www.zhihu.com/search?q=%E5%90%8E%E7%BD%AE%E9%80%9A%E7%9F%A5&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A2352568243%7D)、返回通知、异常通知、环绕通知都实现一遍，并通过调试，把整体的 AOP 流程搞得非常清楚。
* 写一套自定义注解并附上对应的测试用例：现在大家都使用 SpringBoot 了，普遍采用扩展 Spring 的方式就是自定义注解。所以，要理解 Spring 的自定义扩展点，就是要理解 Spring Boot 是如何做到自定义注解的。加载自定义注解，处理自定义注解，最好是通过写出自定义注解的测试用例，然后一步步调试观察出整个流程来。
* 写一个能手动映射 DispatcherServlet 路径的测试用例：在 Spring MVC 中，DispatcherServlet 是所有 web 请求的第一关卡，是非常核心的类。写关于 DispatcherServlet 的测试用例，我建议要想办法通过编码而不是配置去把 DispatcherServlet 相关的路径映射等功能做出来。这对我们理解 Spring MVC 的请求路由，请求映射以及相关核心类的加载和使用都非常重要。
* 写一个自定义的 HttpMessageConverter 加对应的测试用例：自定义 HttpMessageConverter 是我们在使用 Spring 做 web 开发经常要做的一件事情。通过写自定义的 HttpMessageConverter，以及对应的测试用例，对我们理解请求是如何被转化成 Java 对象，Java 对象又是如何转化成我们定义的响应内容格式的这个关键流程是非常重要的。
* 自定义一个 WebDataBinder 并让它生效：使用了 HttpMessageConverter 去转化请求和响应，其中核心的一点是：在请求时如何把参数去绑定到对应的 Java 对象上。而在绑定参数过程中，数据校验也经常和 WebDataBinder 混合在一起。所以理解 WebDataBinder，能更好理解 web 请求到 Spring 中 Java 对象的转化机制。
* 画一张从请求到响应的 Spring MVC 所用到的类的流程图：了解了 Spring MVC 中的几个核心重要类，我们就可以把这些重要类关联起来，并结合一些 Spring MVC 中别的相关类，共同构造出一幅完整的请求-响应流程图，从而加深我们对 Spring MVC 整个体系的理解。
* 自己实现一个 Spring Boot Starter：对于 Spring Boot，我们本身最重要的是去理解 Spring Boot 是如何通过自动配置，把各种 Spring 组件结合在一起的。而这种自动配置，其实就是通过各个组件写自己的 Spring Boot Starter 来完成的。自己实现一个 Spring Boot Starter， 我们就能理解到 Spring Boot 的自动配置、自动加载方法。

再分享一写B上Spring的学习视频（我花了很长时间，根据播放量、点赞量亲自整理的）：

### Spring

**1、2020最新Spring框架教程IDEA版**

57万播放，1.1万赞

**2、狂神说Spring5最新完整教程IDEA版**

129万播放，1.5万赞

**3、尚硅谷Spring5框架最新版教程（idea版）**

90万播放，近万赞

**4、spring源码全集**

13万播放，1.2k赞

**5、spring注解驱动开发-源码版-雷丰阳**

23万播放，2.5k赞

### SpringMVC

**1、SpringMVC最新教程IDEA版**

89万播放，一万赞

**2、SpringMVC 2021最新教程**

18万播放，3千赞

### SpringBoot

**1、雷丰阳2021版SpringBoot2零基础入门**

102万播放，1.4万赞

**2、SpringBoot教程-雷神源码级别讲解**

118万播放，8.6k赞

### SpringCloud

**1、SpringCloud框架开发教程-SpringCloudAlibaba微服务分布式架构**

204万播放，1.8万赞

**2、SpringCloud+Vue项目实战——社交项目**

12万播放，750赞

## 二、学Mybatis

SSM 中的的 M——Mybatis 也最好掌握了，有数据库基础的话，Mybatis 学起来也不算难。

推荐几个B站上的学习视频

**1、狂神说Mybatis最新完整教程IDEA版**

115万播放，1.4万赞

**2、尚硅谷MyBatis实战教程全套完整版**

26万播放，2千赞

## 三、学Netty

Netty 是一套网络框架，我估计程序员从业初期用到的机会不多，但奈何有些面试官会问、会考，所以，若有闲暇功夫，推荐对它看个大概。

Netty 框架让我们能不需要成为网络编程大师，就能写出非常优秀的网络应用。

了解 Netty 框架对咱们也是非常重要的一件事，学习 Netty 框架，推荐《Netty实战》。

![[v2-bf3b15ea95976f9729e1eaf650dd4886_720w.jpg]]
()

这本书，把 Netty 的方方面面讲的很全，Netty 的设计思想也覆盖了大部分，对于熟练使用 Netty 完全够用了。

以上就是学习Java主流框架的方法了，看完有收获的话，可以给我点赞支持一下。

我是 [@四猿外](https://www.zhihu.com/people/5dc7459ebcf5ae18449597fa8dc58213)，**是一名工作十几年的程序员，也是一家上市公司的技术总监，除了以上内容，我还写了很多程序员相关的学习技巧、架构经验、职场生存法则类的优质文章，总结成了一份电子书，我相信你看完之后，对你一定会对你有帮助**。想获取电子书可以戳下面链接。





