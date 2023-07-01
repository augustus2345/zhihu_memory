



详细学习链接：[http://www.cnblogs.com/TankXiao/archive/2012/10/10/2711777.html](https://link.zhihu.com/?target=http%3A//www.cnblogs.com/TankXiao/archive/2012/10/10/2711777.html)

记录一下学习wireshark的笔记

Bg：由于计网课程需要，详细了解一下了该工具（学习网络协议最好的工具）

## wireshark介绍

wireshark的官方下载网站： [http://www.wireshark.org/](https://link.zhihu.com/?target=http%3A//www.wireshark.org/)

wireshark是非常流行的网络封包分析软件，功能十分强大。可以截取各种网络封包，显示网络封包的详细信息。

wireshark是开源软件，可以放心使用。 可以运行在Windows和Mac OS上。 

## Wireshark不能做的

为了安全考虑，wireshark只能查看封包，而不能修改封包的内容，或者发送封包。

## Wireshark VS Fiddler

Fiddler是在windows上运行的程序，专门用来捕获HTTP，HTTPS的。

wireshark能获取HTTP，也能获取HTTPS，但是不能解密HTTPS，所以wireshark看不懂HTTPS中的内容

总结，如果是处理HTTP,HTTPS 还是用Fiddler, 其他协议比如TCP,UDP 就用wireshark

## 同类的其他工具

微软的network monitor

sniffer （都没用过）

## 什么人会用到wireshark

1. 网络管理员会使用wireshark来检查网络问题

2. 软件测试工程师使用wireshark抓包，来分析自己测试的软件

3. 从事socket编程的工程师会用wireshark来调试

4. 听说，华为，中兴的大部分工程师都会用到wireshark。

总之跟网络相关的东西，都可能会用到wireshark.

## wireshark 开始抓包

开始界面

这里重中之重要用管理员权限启动，否则无法读取网卡信息

  


![[v2-721734d6a0938efaa2078786036b6f0c_b.jpg]]
()

  


笔者此时是用校园网连接网络

所以选择的接口WLAN

## Wireshark 窗口介绍

  


![[v2-46823cbf7f9240e70c722c1ad7b37dd5_b.jpg]]
()

  


从上至下依次是

WireShark 主要分为这几个界面

1. Display Filter(显示过滤器)， 用于过滤

2. Packet List Pane(封包列表)， 显示捕获到的封包， 有源地址和目标地址，端口号。 颜色不同，代表

3. Packet Details Pane(封包详细信息), 显示封包中的字段

4. Dissector Pane(16进制数据)

5. Miscellanous(地址栏，杂项)

**Wireshark 显示过滤**

  


![[v2-2fa860a2bbe51e7b7df4a0e5039e012b_b.jpg]]
()

  


使用过滤是非常重要的， 在使用wireshark时，将会得到大量的冗余信息，在几千甚至几万条记录中，为了找到自己需要的部分，所以过滤必不可少。

过滤器会帮助我们在大量的数据中迅速找到我们需要的信息。

过滤器有两种，

一种是显示过滤器，就是主界面上那个，用来在捕获的记录中找到所需要的记录

一种是捕获过滤器，用来过滤捕获的封包，以免捕获太多的记录。 在捕获 -> 捕获过滤器中设置

**保存过滤**

在Filter栏上，填好Filter的表达式后，点击Save按钮， 取个名字。比如"Filter 102"

  


![[v2-65ee8a04d2875a98d25c96e0d76b712f_b.jpg]]
()

  


不管捕获还是显示都可以自己设置增删改查

**过滤表达式的规则**

表达式规则（这里都是采用已有默认的功能）

1. 协议过滤

比如TCP，只显示TCP协议。

2. IP 过滤

比如 ip.src ==192.168.1.102 显示源地址为192.168.1.102，

ip.dst==192.168.1.102, 目标地址为192.168.1.102

3. 端口过滤

tcp.port ==80, 端口为80的

tcp.srcport == 80, 只显示TCP协议的愿端口为80的。

4. Http模式过滤

http.request.method=="GET", 只显示HTTP GET方法的。

5. 逻辑运算符为 AND/ OR

常用的过滤表达式

过滤表达式

用途

http

只查看HTTP协议的记录

ip.src ==192.168.1.102 or ip.dst==192.168.1.102

 源地址或者目标地址是192.168.1.102

这里还有很多笔者只是举了一些例子

## 封包列表(Packet List Pane)

封包列表的面板中显示：

编号，时间戳，源地址，目标地址，协议，长度，以及封包信息。 

你可以看到不同的协议用了不同的颜色显示。你也可以修改这些显示颜色的规则， 视图->着色规则

  


![[v2-66578fde0ba6ef7653b3fc0fb7db3742_b.jpg]]
()

  


## 封包详细信息 (Packet Details Pane)

这个面板是我们最重要的，用来查看协议中的每一个字段。

各行信息分别为

Frame: 物理层的数据帧概况

Ethernet II: 数据链路层以太网帧头部信息

Internet Protocol Version 4: 互联网层IP包头部信息

Transmission Control Protocol: 传输层T的数据段头部信息，此处是TCP

Hypertext Transfer Protocol: 应用层的信息，此处是HTTP协议

  


![[v2-098b7ff177b8279c6f5b3346d3370b31_b.jpg]]
()

  


## wireshark与对应的OSI七层模型

  


![[v2-cab700d0c62bf185c26bdf6c0504531f_b.jpg]]
()





