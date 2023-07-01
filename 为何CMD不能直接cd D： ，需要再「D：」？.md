



在Windows的命令提示符中，当前的驱动器和每个驱动器的当前目录是分开的。你会发现使用D:命令切换到D盘时，它仍然保持着上次的目录，而不是进入根目录。**若要让cd在切换目录的同时更改当前驱动器，应加上/D参数。**如下例：


```
C:\Windows\system32>D:

D:\>cd "Microsoft Office 2016"

D:\Microsoft Office 2016>C:

C:\Windows\System32>D:

D:\Microsoft Office 2016>cd /d "C:\Program Files"

C:\Program Files>
```
也就是说，cd指令默认只会更改每个驱动器的当前目录，而不会更改当前所在的驱动器。如下例：


```
C:\Windows\System32>D:

D:\Visual Studio 2019>C:

C:\Windows\System32>cd "D:\Microsoft Office 2016"

C:\Windows\System32>D:

D:\Microsoft Office 2016>
```
这就可以解答你的疑惑了，因为在你输入cd D:\的时候，当前的驱动器不是D，这条指令的意思是“把D驱动器的当前目录设为根目录”，它的作用和输入cd D:\XXXX\是一样的，自然不会进入D:\目录下了。

但当你输入D:切换时，你会发现D盘的当前目录已经变为根目录。

至于为什么要这样设计，是因为远古时代DOS就是这样设计的，那时候没有图形界面，劳动人民需要频繁使用cd命令在各目录之间切换。如果cd指令总是把当前的驱动器也跟着切换，当你只是想临时照顾一下另一个驱动器的当前目录，旋即继续在当前的驱动器目录下做大量工作，还需要再用一次C:指令切换回来，使操作变得繁琐。



---

最后讲一个几乎被世人遗忘的奇技淫巧，由于每个驱动器的都分别有一个当前目录，我们就可以利用这一点来搞一些事情。如下例：


```
C:\Windows\system32>cd "D:\Microsoft Office 2016\Office16"

C:\Windows\system32>D:winword.exe
```
你会发现Word启动了。

当你需要对另一个驱动器的当前目录下的内容进行操作时，可以使用盘符冒号后面直接跟目录或是文件名的形式。这样一来无需切换当前驱动器，也不用再打一遍完整路径，稍稍偷懒一把。





