



用python写小脚本确实是一件好玩的事情，因为不是个大活儿，而且能解决眼边前十分繁琐的事情，这种轻松且便宜的代码颇受人民群众的欢迎~有点生活小妙招的意味

![[v2-16dcb5beaa4b0940aa5ceee80917e98a_720w.jpg]]
()

大家较为熟知的脚本是用python来做爬虫、抢票、签到、自动回复机器人、批量处理文件等，这些比较常规，还有些较复杂的，比如做物品识别、语义分析、图像处理等，只要你有需求场景，总会想到办法写个小脚本去处理它。

github上有个python项目，里面提供了几百个（可能上千）小脚本，涉及到算法、文件、文本、图像、视频、音乐、爬虫、邮件、可视化、系统、下载等各种常用场景的处理脚本。

![[v2-a22906de6dd92a89d16788889f2ca5f7_720w.jpg]]
()

这个项目不是什么牛逼的大程序，而是作者在日常工作和python学习过程中积累的脚本，一个脚本解决一个问题。获得1万9的赞，说明颇有群众基础。

![[v2-c3ad67b1cc7fe9d8484549683d57e543_720w.jpg]]
()

作者在介绍中所说，他并非专业程序员，而是为了解决问题、提高效率写了这些代码。我也是鼓励初学者可以先按照这种模式来学习编程，从解决问题的角度来写代码，把python当作一把锤子，不断找钉子。

  


![[v2-626dc2e3e54381683f8ae1e1e4379c52_720w.jpg]]
()

很多人会觉得看似简单，但就是写不来，几十行的代码如何能拼拼凑凑变成脚本。我觉得基础不好的更是需要多看语法、多敲代码，不然只能停留在望洋兴叹的阶段。学习这件事从来都是讲方法、看行动的，如果你不知道编程的架构，那买一本python书，仔细研究目录，python有哪些部分组成就能一清二楚。或者跟着老师学，完成每一道编程作业题，也能快速掌握。

分享其中几个脚本：

1、检查主目录中是否存在某文件夹，若不存在则创建


```
# Description : Checks to see if a directory exists in the users home directory, if not then create it

import os  # Import the OS module

MESSAGE = 'The directory already exists.'
TESTDIR = 'testdir'
try:
    home = os.path.expanduser("~")  # Set the variable home by expanding the user's set home directory
    print(home)  # Print the location

    if not os.path.exists(os.path.join(home, TESTDIR)):  # os.path.join() for making a full path safely
        os.makedirs(os.path.join(home, TESTDIR))  # If not create the directory, inside their home directory
    else:
        print(MESSAGE)
except Exception as e:
    print(e)
```
2、打印图片分辨率


```
def jpeg\_res(filename):
   """"This function prints the resolution of the jpeg image file passed into it"""

   # open image for reading in binary mode
   with open(filename,'rb') as img\_file:

       # height of image (in 2 bytes) is at 164th position
       img\_file.seek(163)

       # read the 2 bytes
       a = img\_file.read(2)

       # calculate height
       height = (a[0] << 8) + a[1]

       # next 2 bytes is width
       a = img\_file.read(2)

       # calculate width
       width = (a[0] << 8) + a[1]

   print("The resolution of the image is",width,"x",height)

jpeg\_res("img1.jpg")
```
3、连接MySQL数据库


```
import mysql.connector

# MySQl databses details

mydb = mysql.connector.connect(
    host="0.0.0.0",
    user="root",
    passwd="",
    database="db\_name"
)
mycursor = mydb.cursor()

# Execute SQL Query =>>>> mycursor.execute("SQL Query")
mycursor.execute("SELECT column FROM table")

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```
4、翻转数字


```
n=int(input("Enter number: "))
rev=0
while(n>0):
    dig=n%10
    rev=rev*10+dig
    n=n//10
print("Reverse of the number:",rev)
```
5、PDF转音频


```
import pyttsx3
import pyPDF2
book = open('book.pdf','rb')
pdfreader = pyPDF2.PdfFileReader(book)
pages = pdfreader.numPages
print(pages)
speaker = pyttsx3.init()
page= pdfreader.getpage(7)
text = page.extractText()
speaker.say(text)
speaker.runAndWait()
```
最后：有兴趣的也可以看看相关的Python语法书，很多人都是停留在hello world阶段，第二第三步很难迈出去。其实只要认真看完一门课，学完一本书，编程便不那么难。

如果想少走弯路，不妨看看一些视频课程。自制力比较差的小伙伴，跟着老师把python基础走一遍，效率非常高。

现在市面上好多新出现的python课程，甚至原来做英语的也开始出python产品了，比如百词斩的夜曲编程。我觉得这其实是件好事，说[明学](https://www.zhihu.com/search?q=%E6%98%8E%E5%AD%A6&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1293193482%7D)Python的人越来越多，大家的选择更多元了。

夜曲编程更多面向纯小白，通过图文的形式将编程语法形象化，增加了很多互动学习的机制，比如卡片、闯关、隐喻、奖励等，你在手机、电脑、Pad端都可以学习，不受设备限制。

![[v2-b010d04922a15e8e41e3060a8df1008c_720w.jpg]]
()

而且夜曲里面的课程设置，基本是以实操训练为主，有基础语法、数据分析、爬虫、自动办公等等，还比较符合实用的需求。这有点类似国外的[datacamp](https://www.zhihu.com/search?q=datacamp&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1293193482%7D)，实践性很强。

我仔细看了里面一个Python入门课Pro，好像是有30天基础语法课，加上编程案例实战，同时还有百题斩最擅长的100题闯关。在学习过程中，还可以通过社群提问进行问题答疑，有专门的老师在群里。

![[v2-5b8b08b16bab48ea769869fc65b1376f_720w.jpg]]
()

如果你是纯小白，那可以试试夜曲的Python基础体验课程，总共6节，还有7天社群共学+助教答疑服务，和13道百题斩练习（代码实操练习题），学习完一般可以入门了。

现在都流行非IDE编程，夜曲的网站和app内嵌了代码编辑器，可以直接在网页或手机上敲代码并运行，对小白很友好，当然我还是建议大家有能力自己装IDE写代码。

大家可以去试试看，对照的语法书来学，应该很快可以入门。

一直在创作python&数据内容，从未停止哈哈，觉得不错点个关注[朱卫军](https://www.zhihu.com/people/pydatalysis)~

还有之前梳理的python选书小诀窍，推荐大家也看看：





