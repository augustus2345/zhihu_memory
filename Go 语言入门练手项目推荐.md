



**重磅更新！**

我为大家带来了一个**全新的系列课程 《[从零实现 KV 存储](https://www.zhihu.com/search?q=%E4%BB%8E%E9%9B%B6%E5%AE%9E%E7%8E%B0%20KV%20%E5%AD%98%E5%82%A8&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A2927645028%7D)》，采用 Rust 和 Go 两种语言实现，兼容 Redis 协议，并且是手把手教学**，教学视频中会演示每一行代码的编写，保证你能够学懂学透！

并且只需要掌握基础的 Go 语法知识即可，课程中涉及到的一些知识我都会详细的进行讲解。

关于课程详情，其他 Q&A 等，可以看这里：



---

大家好，我是 roseduan，经常看到一些小伙伴学习完 Go 语言的基础知识之后，无法找到合适的练手项目，然后就很迷茫。

今天我向大家推荐几个我觉得还不错的 Go 语言入门练手项目，你可以根据自己的兴趣，选择一个合适的，自己去看看，学习一下。

在这之前，需要说明一下，很多人看到别人的项目代码一头雾水，完全没有头绪，这是很正常的。因为别人的项目，可能是经历很长时间，花了大量时间辛辛苦苦维护的，你千万别想着花一两个小时就能完全看懂了，还是要有点耐心的。

当然，如果你是万中无一的绝世高手，那么就随意啦！

### **1、gin-vue-admin**


> Github 地址：[https://github.com/flipped-aurora/gin-vue-admin](https://link.zhihu.com/?target=https%3A//github.com/flipped-aurora/gin-vue-admin)  
> Star 数量：7.6k

![[v2-5b5cc167acc37e99e8f174806a21cf15_b.jpg]]
()

gin-vue-admin 是一个使用 gin + vue 进行极速开发的全栈后台管理系统，后台使用 gin 框架，gin 是目前很流行的 Go 语言 web 框架，前端主要使用 vue。

项目的目录结构非常清晰，包名语义化，能够帮助你快速上手学习。

这个项目还使用到了一些流行的 Go 开源库及中间件，例如：

* gin：最流行的 Go 语言 web 框架
* gorm：数据库操作中间件
* zap：uber 开源的 Go 语言日志库
* redis：k-v 缓存

这个项目还有详细的中文文档，并且配套教学视频，值得学习！

### **2、ferry**


> Github 地址：[https://github.com/lanyulei/ferry](https://link.zhihu.com/?target=https%3A//github.com/lanyulei/ferry)  
> Star 数量：3.3k

![[v2-62e8f75248930d8643c67a15a2ea22bd_b.jpg]]
()

基于 Gin + Vue + Element UI 前后端分离的工单系统，集工单统计、任务钩子、权限管理、灵活配置流程与模版等等于一身的开源工单系统，当然也可以称之为工作流引擎。

 致力于减少跨部门之间的沟通，自动任务的执行，提升工作效率与工作质量，减少不必要的工作量与人为出错率。

项目当中涉及到的一些其他的中间件：

* casbin：访问控制工具
* gorm：数据库操作中间件
* zap：uber 开源的 Go 语言日志库

### **3、Yearning**


> Github 地址：[https://github.com/cookieY/Yearning](https://link.zhihu.com/?target=https%3A//github.com/cookieY/Yearning)  
> Star 数量：5.2k

![[v2-8c011ac3e5c66b8cd2e54a4441af4328_b.jpg]]
()

Yearning 是一个高颜值 sql 审核平台，是真的高颜值，界面设计非常的漂亮，看起来很舒服！

Yearning 拥有多项实用型功能，助力 DBA 提升工作自动化、标准化，主要的功能有：

* 自动化 SQL 语句审核，可对 SQL 进行自动检测并执行
* DDL/DML 语句执行后自动生成回滚语句
* 审核、查询、审计功能
* 支持 LDA P登录/钉钉及邮件消息推送
* 支持自定义审核工作流
* 支持细粒度权限分配

项目中使用了作者本人自研的 web 框架，还有其他的一些中间件：gorm、tidb、grpc。

还有详细的中文文档。

### **4、Go-admin**


> Github 地址：[https://github.com/go-admin-team/go-admin](https://link.zhihu.com/?target=https%3A//github.com/go-admin-team/go-admin)  
> Star 数量：3.9k

![[v2-9d8067a33abf37b41bf8b67a9334e6e0_b.jpg]]
()

这是一个基于 Gin + Vue + Element UI 的前后端分离权限管理系统，特性如下：

* 遵循 RESTful API 设计规范
* 基于 GIN WEB API 框架，提供了丰富的中间件支持（用户认证、跨域、访问日志、追踪ID等）
* 基于 Casbin 的 RBAC 访问控制模型
* JWT 认证
* 支持 Swagger 文档(基于 swaggo)
* 基于 GORM 的数据库存储，可扩展多种类型数据库
* 配置文件简单的模型映射，快速能够得到想要的配置
* 代码生成工具
* 表单构建工具
* 多命令模式

项目有详细中文文档和配套视频教程！

### **5、wechat-go**


> Github 地址：[https://github.com/songtianyi/wechat-go](https://link.zhihu.com/?target=https%3A//github.com/songtianyi/wechat-go)  
> Star 数量：1.4k

![[v2-553440a3147f5ee64febc7458e0c17e8_b.jpg]]
()

这是微信 web 版 API 的 Go y语言实现，模拟微信网页版的登录／联系人／消息收发等功能，可以完全接管微信收到的消息，并定制自己的发送内容。

我觉得这个项目还是挺有趣的，用来操作一下微信，能够体会到更多学习的乐趣。

### **7days-golang**


> Github 地址：[https://github.com/geektutu/7days-golang](https://link.zhihu.com/?target=https%3A//github.com/geektutu/7days-golang)  
> Star 数量：7k

这是一个七天从零用 Go 实现简易版项目的系列，主要有：

* Web框架 - Gee
* 分布式缓存 GeeCache
* ORM框架 GeeORM
* RPC框架 GeeRPC

虽然说是用七天实现，但是还是有一些难度的，想要挑战一下自己的同学，可以尝试学习一下这个项目！

而且，还是建议刚入门Go语言的同学要多刷一些基础题，可以去牛客网上看看，里面有很多适合新手做的Go语言入门题（提升更快~）

![[v2-595155bd288018012d1861741530d433_b.jpg]]
()

这一期的分享就到这啦，欢迎关注我，后续还有分享更多更有趣、更实用的 Go 语言内容哦！





