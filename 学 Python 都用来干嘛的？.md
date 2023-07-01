



## 可以拿来了解女朋友情绪变化，顺道自动回复。

还能一键扣图，让开淘宝店的设计师下岗，在一旁痛哭流涕……

  



> **提示：关注微信公众号 【七月在线实验室】，让自己变得更强！在公众号内发“ZH”。即可获得BAT面试题100道和课程代金劵等精美好礼哦！**

  


## 一


> 虽然程序员不会有女朋友，但是这个也可以用在同性朋友身上哦。

再也不用担心工作忙，没法经常和她/他/它聊天了。

可以实时知道女友的情感情绪指数，再也不用担心女友莫名其妙生气了。

还能顺道教女朋友学英语（女朋友一定很惊喜）

为了方便快速开发，我们使用python中的wxpy模块完成微信的基本操作。

首先，我们设置一个config.ini配置文件，并从这个配置文件开始读取信息。这些参数一看就懂，所以无需多言。


```
# 读取配置文件
cf = configparser.ConfigParser()
cf.read("./config.ini",encoding='UTF-8')

# 设置女友的微信名称，记住，不是微信ID也不是微信备注
# 你女友的微信名称，记住，不是微信ID也不是微信备注
my_lady_wechat_name = cf.get("configuration", "my_lady_wechat_name")

# 设置早上起床时间，中午吃饭时间，下午吃饭时间，晚上睡觉时间
say_good_morning = cf.get("configuration", "say_good_morning")
say_good_lunch = cf.get("configuration", "say_good_lunch")
say_good_dinner = cf.get("configuration", "say_good_dinner")
say_good_dream = cf.get("configuration", "say_good_dream")

# 设置女友生日信息
# 几月，注意补全数字，为两位数，比如6月必须写成06
birthday_month = cf.get("configuration", "birthday_month")
# 几号，注意补全数字，为两位数，比如6号必须写成08
birthday_day = cf.get("configuration", "birthday_day")

# 读取早上起床时间，中午吃饭时间，下午吃饭时间，晚上睡觉时间的随机提示语
# 一般这里的代码不要改动，需要增加提示语可以自己打开对应的文件修改
#早上起床问候语列表，数据来源于新浪微博
str_list_good_morning = ''
with open("./remind_sentence/sentence_good_morning.txt", "r",encoding='UTF-8') as f:
    str_list_good_morning = f.readlines()
print(str_list_good_morning)

#中午吃饭问候语列表，数据来源于新浪微博
str_list_good_lunch = ''
with open("./remind_sentence/sentence_good_lunch.txt", "r",encoding='UTF-8') as f:
    str_list_good_lunch = f.readlines()
print(str_list_good_lunch)

#晚上吃饭问候语列表，数据来源于新浪微博
str_list_good_dinner = ''
with open("./remind_sentence/sentence_good_dinner.txt", "r",encoding='UTF-8') as f:
    str_list_good_dinner = f.readlines()
print(str_list_good_dinner)

#晚上睡觉问候语列表，数据来源于新浪微博
str_list_good_dream = ''
with open("./remind_sentence/sentence_good_dream.txt", "r",encoding='UTF-8') as f:
    str_list_good_dream = f.readlines()
print(str_list_good_dream)

# 设置晚上睡觉问候语是否在原来的基础上再加上每日学英语精句
# False表示否 True表示是
if((cf.get("configuration", "flag_learn_english")) == '1'):
    flag_learn_english = True
else:
    flag_learn_english = False
print(flag_learn_english)
# 设置所有问候语结束是否加上表情符号
# False表示否 True表示是
str_emoj = "(•‾̑⌣‾̑•)✧˖°----(๑´ `๑)----(๑¯ิε ¯ิ๑)----(๑•́ ₃ •̀๑)----( ∙̆ .̯ ∙̆ )----(๑˘ ˘๑)----(●′ω`●)----(●･̆⍛･̆●)----ಥ_ಥ----_(:qゝ∠)----(´；ω；`)----( `)3')----Σ((( つ•̀ω•́)つ----╰(*´︶`*)╯----( ´´ิ∀´ิ` )----(´∩｀。)----( ื▿ ื)----(｡ŏ_ŏ)----( •ิ _ •ิ )----ヽ(*΄◞ิ౪◟ิ‵ *)----( ˘ ³˘)----(; ´_ゝ`)----(*ˉ﹃ˉ)----(◍'౪`◍)ﾉﾞ----(｡◝‿◜｡)----(ಠ .̫.̫ ಠ)----(´◞⊖◟`)----(。≖ˇェˇ≖｡)----(◕ܫ◕)----(｀◕‸◕´+)----(▼ _ ▼)----( ◉ืൠ◉ื)----ㄟ(◑‿◐ )ㄏ----(●'◡'●)ﾉ♥----(｡◕ˇ∀ˇ◕）----( ◔   ◔ )----( ´◔ ‸◔`)----(☍﹏⁰)----(♥◠‿◠)----ლ(╹◡╹ლ )----(๑꒪◞౪◟꒪๑)"
str_list_emoj = str_emoj.split('----')
if ((cf.get("configuration", "flag_wx_emoj")) == '1'):
    flag_wx_emoj = True
else:
    flag_wx_emoj = False
print(str_list_emoj)

# 设置节日祝福语
# 情人节祝福语
str_Valentine = cf.get("configuration", "str_Valentine")
print(str_Valentine)

# 三八妇女节祝福语
str_Women = cf.get("configuration", "str_Women")
print(str_Women)

# 平安夜祝福语
str_Christmas_Eve = cf.get("configuration", "str_Christmas_Eve")
print(str_Christmas_Eve)
# 圣诞节祝福语
str_Christmas = cf.get("configuration", "str_Christmas")
print(str_Christmas)

# 她生日的时候的祝福语
str_birthday = cf.get("configuration", "str_birthday")
print(str_birthday)
```
设置完相关参数以后，我们再来学习一下，如何每天教女友学英语：


```
# 获取每日励志精句
def get_message():
    r = requests.get("http://open.iciba.com/dsapi/")
    note = r.json()['note']
    content = r.json()['content']
    return note,content
```
如果你愿意，可以在上面对时间的判断中，加入一些其他你想要的，这样你女友就更开心啦！后期如果有时间，我将会加上以上节日问候功能。

接着，开启微信机器人，为了程序的健壮性，自动判断一下操作系统，根据不同操作系统执行不同指令：


```
# 启动微信机器人，自动根据操作系统执行不同的指令
# windows系统或macOS Sierra系统使用bot = Bot()
# linux系统或macOS Terminal系统使用bot = Bot(console_qr=2)
if('Windows' in platform.system()):
    # Windows
    bot = Bot()
elif('Darwin' in platform.system()):
    # MacOSX
    bot = Bot()
elif('Linux' in platform.system()):
    # Linux
    bot = Bot(console_qr=2,cache_path=True)
else:
    # 自行确定
    print("无法识别你的操作系统类型，请自己设置")
```
只有每天的问候和节日问候是仅仅不够的，我们必须时刻知道她的情绪指数，这里可以使用snowNlp或者jieba来做分析，但是为了能够在打包成exe可执行文件时使得程序尽可能小，我们采取直接调用接口的方式来做。代码如下：


```
# 接收女友消息监听器
# 女友微信名
my_girl_friend = bot.friends().search(my_lady_wechat_name)[0]
# chats=my_girl_friend 表示接收消息的对象，也就是女友
# except_self=False 表示同时也接收自己发的消息，不需要接收自己消息的可以去掉
@bot.register(chats=my_girl_friend, except_self=False)
def print_others(msg):
    # 输出聊天内容
    print(msg.text)

    # 做极其简单的情感分析
    # 结果仅供参考，请勿完全相信
    postData = {'data':msg.text}
    response = post('https://bosonnlp.com/analysis/sentiment?analysisType=',data=postData)
    data = response.text

    # 情感评分指数(越接近1表示心情越好，越接近0表示心情越差)
    now_mod_rank = (data.split(',')[0]).replace('[[','')
    print("来自女友的消息:%s\n当前情感得分:%s\n越接近1表示心情越好，越接近0表示心情越差，情感结果仅供参考，请勿完全相信！\n\n" % (msg.text, now_mod_rank))

    # 发送信息到文件传输助手
    mood_message = u"来自女友的消息:" + msg.text + "\n当前情感得分:" + now_mod_rank + "\n越接近1表示心情越好，越接近0表示心情越差，情感结果仅供参考，请勿完全相信！\n\n"
    bot.file_helper.send(mood_message)
```
教完女友学英语后，开始把我们的关心语发给她。这里涉及到wxpy模块的相关操作，很简单，看我的例子就会了：


```
# 发送消息给她
def send_message(your_message):
    try:
        # 对方的微信名称
        my_friend = bot.friends().search(my_lady_wechat_name)[0]

        # 发送消息给对方
        my_friend.send(your_message)
    except:

        # 出问题时，发送信息到文件传输助手
        bot.file_helper.send(u"守护女友出问题了，赶紧去看看咋回事~")
```
最后，就是如何每天定时发关心语给女友的问题了。

首先来个while循环，365天无限关心


```
# 来个死循环，24小时关心她
    while(True):

        # 提示
        print("守护中，时间:%s"% time.ctime())

        # 每天定时问候，早上起床，中午吃饭，晚上吃饭，晚上睡觉
        # 获取时间，只获取时和分，对应的位置为倒数第13位到倒数第8位
        now_time = time.ctime()[-13:-8]
        if (now_time == say_good_morning):
            # 随机取一句问候语
            message = choice(str_list_good_morning)

            # 是否加上随机表情
            if(flag_wx_emoj):
                message = message + choice(str_list_emoj)

            send_message(message)
            print("提醒女友早上起床:%s" % time.ctime())

        …………这下面还有很多代码，我就不列出来了…………
   # 延时60秒
   time.sleep(60)
```
最后，输入以下代码开始守护女友模式吧~


```
# 开始守护女友
    t = Thread(target=start_care, name='start_care')
    t.start()
```
## **使用教程**

**pip安装下列包：**

* [x] pip install wxpy
* [x] pip install requests

**设置以下内容：**


```
[configuration]

# 设置女友的微信名称，记住，不是微信ID也不是微信备注
my_lady_wechat_name = 小强子

# 设置女友生日信息
# 若某一项月份或者日期不想设置，请输入99，不能留空
# 几月，注意补全数字，为两位数，比如6月必须写成06
birthday_month = 03
# 几号，注意补全数字，为两位数，比如6号必须写成08
birthday_day = 18

# 设置早上起床时间，中午吃饭时间，下午吃饭时间，晚上睡觉时间
# 若某一项时间不想设置，请输入99:00，不能留空
say_good_morning = 03:09
say_good_lunch = 03:10
say_good_dinner = 03:11
say_good_dream = 03:12

# 设置晚上睡觉问候语是否在原来的基础上再加上每日学英语精句
# 1表示是，0表示否
flag_learn_english = 1

# 设置所有问候语结束是否加上表情符号
# 1表示是，0表示否
flag_wx_emoj = 1

# 设置节日祝福语
# 情人节祝福语
str_Valentine = 亲爱的，情人节快乐！我想和你一起分享生命中的每一天，直到永远。

# 三八妇女节祝福语
str_Women = 嘿，女神节到了，祝我的女神开心快乐！你每天都是那么好看^_^

# 平安夜祝福语
str_Christmas_Eve = 宝贝，平安夜快乐，你吃苹果了吗？n(*≧▽≦*)n

# 圣诞节祝福语
str_Christmas = 小仙女，圣诞节快乐哦！（づ￣3￣）づ╭❤～

# 她生日的时候的祝福语
str_birthday = 亲爱的，生日快乐，我已经给你准备好了礼物哦，明天你就能看到啦！(*@ο@*) 哇～
```
## **演示图片**

![[v2-261107441d6360c6d6613a6eeb5909dd_720w.jpg]]
()

![[v2-d024629ab74c8f0bed5a5d1b03521b8e_720w.jpg]]
()

![[v2-1e80d9ee17243edd31179ea07b623c43_720w.jpg]]
()

![[v2-529ae3495da2e9cfee7d6740a6a23401_720w.jpg]]
()


> 原作者：云外孤岛 [http://www.cnblogs.com/cloudbird/p/10534658.html](https://link.zhihu.com/?target=http%3A//www.cnblogs.com/cloudbird/p/10534658.html)

至于没有女朋友的……

要不考虑一下它

![[v2-fc43db93b5cc0608867898bb2778376f_720w.jpg]]
()

## 二


> 本段转载自：高级农民工（ID：Mocun6）

这张逼死淘宝专业抠图店家的照片，用3行Python代码，花5秒就能超高精度抠图。

![[v2-93597216b728630ae6f6ebc9213f1d4d_720w.jpg]]
()

![[v2-80dc9df62c9ea9eb747ee8a4df81e731_720w.jpg]]
()

![[v2-09cee6122d5771cf0bc7d9792b6c80be_720w.jpg]]
()

这里的 API 接口来源于 Remove.bg 网站，一个邮箱账号可以申请一个免费接口，可处理 50 张照片，如果想处理更多或者生成高清照片，需要买套餐，算下来价格大概是 **1 元一张**。

上淘宝搜索「**证件照换底色**」的店铺，发现多数店铺收费是 **5 元**，觉得利用好价格差空间，应该有商机。

接着比较感兴趣淘宝店家是怎么抠图的，抠图的质量如何，于是选择了排名前两位的店家来做测试，跟掌柜开始了一段「**套路**」聊天。

![[v2-92136ca60c394e9d44960e6558ca2eed_720w.jpg]]
()

先找了第一家店主，店主上来就说先发照片，抠图满意再付款，于是就发了文章开头那张比较难抠的一张，想看看他们水平怎么样：

![[v2-eb5108a0294e665a61df8086955e172c_720w.jpg]]
()

没想到店主这一抠就是二十分钟。。。

满心期待地打开图片一看，头发丝抠的不好，照片色彩也变了：

![[v2-4b63c7daf07aa9b760d9da70bfbf7127_720w.jpg]]
()

跟第二家店掌柜聊了后，也是花了 16 分钟弄好，比第一家稍好一点：

![[v2-a695e18788f30c7d9f86883d145c479a_720w.jpg]]
()

把三幅图一对比，从头发丝抠的效果和照片的色彩还原度就可以看出还是 AI 效果最好，而且只需要 5 秒钟。

于是，大致可以总结**这款 AI 工具从效果和效率上基本碾压手动 PS 的淘宝店家。**

![[v2-ef1e13253d65ca4e4bd351c184df93fc_720w.jpg]]
()

心疼掌柜，花了 20 分钟还没有拿下我这一单……

这么难抠的图 AI 工具效果都好，那简单的证件照应该更没问题，基本确定有商机。

  


  




---

  


  


接下来用 Python 把上面的代码进行完善打包成 exe 文件执行。

轻松实现这样的功能：**只需要简单敲几下键盘，就可以随意批量更换照片的背景色**（常见的白、蓝、红三种颜色），**然后秒换背景出图**。

效果如下：

![[v2-26b27a75eb55c868dc893e411d6a8f31_720w.gif]]
()

具体实现很简单，第一步输入 API，第二步输入图片所在文件夹，接着程序就会先抠图，生成带透明背景的 PNG 格式图形。 

接下来第三步利用 PIL 库来设置图片的背景颜色，键入一个字母就可以秒生成对应的背景色证件照。

* b：blue 蓝色
* r：red 红色
* w：white 白色

这样就做成了一个简单的证件照更换工具，拿去开个淘宝店和抠图的设计师抢饭吃没有压力……

估计打死店主也都想不到让自己下岗的是几行代码……效率还是自己的N倍……

此工具可关注公众号“七月在线实验室”后，发“证件照”获取。

  


## **转载自公众号“七月在线实验室”**

**↓**↓↓

**公号后台回复“666”。即可免费获得 七月在线【面试求职 第四期】课程+最新升级版《名企AI面试100题》电子书。**

![[v2-6f13a2c6b4158fc14ee50e8299b62bde_720w.jpg]]
()

![[v2-918d9244cb11362b27bce59a32c3466e_720w.jpg]]
()

  


《名企AI⾯试100题》涵盖**计算机语⾔基础、算法和⼤数据、机器学习、深度学习、应⽤⽅向 (CV NLP 推荐 ⾦融风控)等五⼤章节**，每⼀段代码、每⼀道题⽬的解析都经过了反复审查或review。

**部分内容展示**

![[v2-0d61ae9e352e05e24db7631ed6389551_720w.jpg]]
()

![[v2-310b312d4c8ab605a5e32c92cf6c6d45_720w.jpg]]
()

![[v2-883648bbf11b54cdb98069c061aab4eb_720w.jpg]]
()

（点击图片可查看大图）



