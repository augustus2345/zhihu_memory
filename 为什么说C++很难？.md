



因为，不同的语言习惯使用在不同的领域；而C++的使用领域就要求你使用它的“可怕特性”。

  


打个比方的话，python大概就相当于这个：

![[v2-837a385f9e14ec3c1dae28b0b5f1841a_720w.jpg]]
()

写个爬虫当好胶水，足够了；没人指望你用它来实现个TCP协议栈。

  


而C++呢？

![[v2-284eb03d406ccf085b52ec2ad629de6b_720w.jpg]]
()

  


你当然也可以拿它来削铅笔——反正所有编程语言都是与或非顺序分支循环那么几个套路，对吧。

它当然能削铅笔。

  


问题是，你觉得，什么样的老板会拿出足够雇佣高级木匠的价格，雇个只管削铅笔的人？



---

C/C++的设计，就是为了下写OS上写库的。

  


所以，它压根不在乎“有没有好用的string类”“能不能支持垃圾回收”——是的，是的，它们有用。

但，如果因为引入它们、耽误了程序员“内存雕花”的本职工作，那就太得不偿失了。

  


别的语言，可以把内存模型彻底藏起来，让程序员不知道还有内存分配这回事：你只管写你的逻辑，别的都交给我！

可C/C++不行。

  


或者说，当你写一个入门级的爬虫时，的确无需知道内存、二进制协议等杂七杂八的东西，用python足够了；但，当你需要写电信级的支柱性工程，比如尽可能用现有硬件支持更大规模的互联网访问时，把网络流量响应速度尽可能提高以便更充分利用设备的吞吐能力时，你可不能不会管内存管其他一切资源——更不可能不会用指针。

  


类似的，当你的目标仅仅是“为xx公司的xx程序写一个界面”时，python足够你用了——其实js都足够你用了。

什么软件工程、多态，什么接口稳定……你统统不需要管。堆屎山就是了。

但，当你的目标是“在所有的设备，包括低功耗的嵌入式/可穿戴设备以及高性能PC上面，提供一套傻瓜式开发库”“让傻瓜拖拖拉拉都能搞出漂亮的界面”时，你就必须算无遗策——别不光“傻瓜拖拉一下就会用”这个目标你都达不到，甚至连“让专家三天学会”都不可能……

那么这时候，多态，类型自动转换，模板，编译期计算……各种奇技淫巧，它们的作用就来了。

  


为什么？



---

举例来说，你之所以在python中可以“不用声明变量类型”，是因为它实际上存储于类似这样的数据结构中：


```
typedef struct tagVARIANT {
union {
     struct {
       VARTYPE vt;
       WORD    wReserved1;
       WORD    wReserved2;
       WORD    wReserved3;
       union {
         LONGLONG     llVal;
         LONG         lVal;
         BYTE         bVal;
         SHORT        iVal;
         FLOAT        fltVal;
         DOUBLE       dblVal;
         VARIANT\_BOOL boolVal;
         VARIANT\_BOOL \_\_OBSOLETE\_\_VARIANT\_BOOL;
         SCODE        scode;
         CY           cyVal;
         DATE         date;
         BSTR         bstrVal;
         IUnknown     *punkVal;
         IDispatch    *pdispVal;
         SAFEARRAY    *parray;
         BYTE         *pbVal;
         SHORT        *piVal;
         LONG         *plVal;
         LONGLONG     *pllVal;
         FLOAT        *pfltVal;
         DOUBLE       *pdblVal;
         VARIANT\_BOOL *pboolVal;
         VARIANT\_BOOL *\_\_OBSOLETE\_\_VARIANT\_PBOOL;
         SCODE        *pscode;
         CY           *pcyVal;
         DATE         *pdate;
         BSTR         *pbstrVal;
         IUnknown     **ppunkVal;
         IDispatch    **ppdispVal;
         SAFEARRAY    **pparray;
         VARIANT      *pvarVal;
         PVOID        byref;
         CHAR         cVal;
         USHORT       uiVal;
         ULONG        ulVal;
         ULONGLONG    ullVal;
         INT          intVal;
         UINT         uintVal;
         DECIMAL      *pdecVal;
         CHAR         *pcVal;
         USHORT       *puiVal;
         ULONG        *pulVal;
         ULONGLONG    *pullVal;
         INT          *pintVal;
         UINT         *puintVal;
         struct {
           PVOID       pvRecord;
           IRecordInfo *pRecInfo;
         } \_\_VARIANT\_NAME\_4;
       } \_\_VARIANT\_NAME\_3;
     } \_\_VARIANT\_NAME\_2;
     DECIMAL decVal;
   } \_\_VARIANT\_NAME\_1; } VARIANT;

```
以上引自微软的这个文档：[VARIANT (oaidl.h) - Win32 apps | Microsoft Learn](https://link.zhihu.com/?target=https%3A//learn.microsoft.com/en-us/windows/win32/api/oaidl/ns-oaidl-variant)

  


这玩意儿看起来复杂，思路倒也简单：用vt指示union中当前储存的数据是什么类型，然后暴力罗列所有需要处理的数据类型（反正是共用内存，浪费不了太多）。

然后，利用函数类型声明、模板的类型推导/类型萃取等等机制，以及类自动类型转换等机制触发正确的转换函数，从而使得“你需要什么类型，我就把用户数据转换过去、确保调用成功”。

  


正因为我们C/C++程序员在背后做了这个玩意儿，python程序员才可以“不管变量类型”。

  


但，正如你所见，C++里面，自动类型转换可能是它最大的坑，没有之一。

你当然可以绕开，这没问题。但，“绕开”这个选择本身，也就意味着你不可能涉足“通用库代码编写”这个领域了——很显然的，想要涉足这个领域，你不光不能绕开，还必须迎难而上、把C++相关特性（那个最深的坑）玩的出神入化。

  


类似的，模板诘屈聱牙？绕开？

可以。

但绕开了，你基本就别再想涉足“通用数值计算库”等领域了。

  


你看，你可以绕开其中的每个难点；但所有难点都绕开之后……

我建议你还是学python吧。

因为现在你用c++能实现的东西，和用python是一样多的；但python有完善而丰富的高阶库，从字符串处理到图形界面再到垃圾回收，什么都有；在它的帮助下，你几乎什么都能做……

但C++可没有那么多那么简单的傻瓜库——没错，python有Qt，而Qt就是C++自己搞的；但C++的Qt可没有内存回收也没有python那么爽的字符串切片json字典可以用——既然你早就选择绕开了，显然靠你自己是写不出这些基本功能的。

你看，你拿c++当python用，它实际上就还不如python——至少你得有能力把内存管理拿回来，不然……

找一个愿意花钱雇高级木匠、工作却是专职削铅笔的老板，或许并不是那么容易。

  


当然，具体工作中，我们C++程序员当然不会傻愣愣的非要把自己知道的所有高级特性都拿进来、用一用。事实上，“尽量动用更少的C++特性”反而是我们这些从业者的经验之谈。

但，“尽量动用更少的特性”的前提是，这些特性足够解决我们的问题——为了提高代码质量、少用C++特性，老板，我们的工程搞不定了：这就成笑话了，对吧。

  


事实上，和C++程序员面对的任务相比，语言本身那点特性根本不难。都是些一眼看懂的玩意儿。

但，怎么用好它、伺候好那些使用我们的API的“傻瓜”，这事实在太难。

  


实践中，甚至可能是，为了实现某些非常好的特性，业界甚至不惜继续扩充C++！

典型如Qt，为了支持signal-slot-bind机制，不得不专门搞一个预处理器。不然C++本身是做不到“bind时，自动检查signal-slot的有效性、匹配性”的。

这东西你当然可以绕开，然后像MFC一样，强迫程序员（用户）敲一堆看上去很像但错一点就要命而且不会有提示的宏，没问题啊。

但你猜为什么MFC很早就被微软自己放弃了？



---

综上。C++难，绝不是难在它有坑、有难以让初学者理解的各种特性；而是，你可以在内部极尽聪明，但却必须写出稳定、可靠的程序，这样才不需要逼你的使用者看你的逻辑；同时，你还要给出简洁、易理解、傻瓜都会用的接口（以及易读易理解的接口文档）——并把你内部的、复杂的东西都严严实实藏好。

  


反过来说也对：很多C++开发者是没有能力把自己用到的、复杂的特性藏好的；这种“泄漏”会强迫合作开发者也学会相关复杂特性……这种难以隔断的“传染”也会使得那些对常用特性一无所知的初学者难以融入团队，除非他们搞明白了团队用到的各种特性。





