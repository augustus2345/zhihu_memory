



大概是因为实在太友好了吧。

## 一. 可以制作一些有趣的小玩意

比如仿制抖音之前很火的表白小软件，效果如下：

[![[v2-70294241dd6a3811763ff66be5cb8bf1_b.jpg]]
()

https://www.zhihu.com/video/1013539038300684288](https://link.zhihu.com/?target=https%3A//www.zhihu.com/video/1013539038300684288)介绍：

源代码如下：


```
# Python制作仿抖音表白神器
# 作者: Charles
# 公众号: Charles的皮卡丘
# 代码仅供学习交流，不得用于其他
import os
import sys
import random
import pygame
from pygame.locals import *


WIDTH, HEIGHT = 640, 480
BACKGROUND = (255, 255, 255)
if getattr(sys, 'frozen', False):
        # 打包音频等文件时
        CurrentPath = sys._MEIPASS
        # 不打包音频等文件时
        # CurrentPath = os.getcwd()
else:
        CurrentPath = os.path.dirname(__file__)
FONTPATH = os.path.join(CurrentPath, 'simkai.ttf')
MUSICPATH = os.path.join(CurrentPath, '1.mp3')
IMGPATH = os.path.join(CurrentPath, '1.png')


# 按钮
def button(text, x, y, w, h, color, screen):
        pygame.draw.rect(screen, color, (x, y, w, h))
        font = pygame.font.Font(FONTPATH, 20)
        textRender = font.render(text, True, (0, 0, 0))
        textRect = textRender.get_rect()
        textRect.center = ((x+w/2), (y+h/2))        
        screen.blit(textRender, textRect)


# 标题
def title(text, screen, scale, color=(255, 0, 0)):
        font = pygame.font.Font(FONTPATH, WIDTH//(len(text)*2))
        textRender = font.render(text, True, color)
        textRect = textRender.get_rect()
        textRect.midtop = (WIDTH/scale[0], HEIGHT/scale[1])
        screen.blit(textRender, textRect)


# 生成随机的位置坐标
def get_random_pos():
        x, y = random.randint(20, 620), random.randint(20, 460)
        return x, y


# 点击喜欢按钮后显示的页面
def show_like_interface(text, screen, color=(255, 0, 0)):
        screen.fill(BACKGROUND)
        font = pygame.font.Font(FONTPATH, WIDTH//(len(text)))
        textRender = font.render(text, True, color)
        textRect = textRender.get_rect()
        textRect.midtop = (WIDTH/2, HEIGHT/2)
        screen.blit(textRender, textRect)
        pygame.display.update()
        while True:
                for event in pygame.event.get():
                        if event.type == QUIT:
                                pygame.quit()
                                sys.exit()


# 主函数
def main():
        pygame.init()
        screen = pygame.display.set_mode((WIDTH, HEIGHT), 0, 32)
        pygame.display.set_caption('FROM一个喜欢你很久的小哥哥')
        clock = pygame.time.Clock()
        pygame.mixer.music.load(MUSICPATH)
        pygame.mixer.music.play(-1, 30.0)
        pygame.mixer.music.set_volume(0.25)
        unlike_pos_x = 330
        unlike_pos_y = 250
        unlike_pos_width = 100
        unlike_pos_height = 50
        unlike_color = (0, 191, 255)
        like_pos_x = 180
        like_pos_y = 250
        like_pos_width = 100
        like_pos_height = 50
        like_color = (0, 191, 255)
        running = True
        while running:
                screen.fill(BACKGROUND)
                img = pygame.image.load(IMGPATH)
                imgRect = img.get_rect()
                imgRect.midtop = int(WIDTH/1.3), HEIGHT//7
                screen.blit(img, imgRect)
                for event in pygame.event.get():
                        if event.type == pygame.MOUSEBUTTONDOWN:
                                mouse_pos = pygame.mouse.get_pos()
                                if mouse_pos[0] < like_pos_x+like_pos_width+5 and mouse_pos[0] > like_pos_x-5 and\
                                        mouse_pos[1] < like_pos_y+like_pos_height+5 and mouse_pos[1] > like_pos_y-5:
                                        like_color = BACKGROUND
                                        running = False
                mouse_pos = pygame.mouse.get_pos()
                if mouse_pos[0] < unlike_pos_x+unlike_pos_width+5 and mouse_pos[0] > unlike_pos_x-5 and\
                        mouse_pos[1] < unlike_pos_y+unlike_pos_height+5 and mouse_pos[1] > unlike_pos_y-5:
                        while True:
                                unlike_pos_x, unlike_pos_y = get_random_pos()
                                if mouse_pos[0] < unlike_pos_x+unlike_pos_width+5 and mouse_pos[0] > unlike_pos_x-5 and\
                                        mouse_pos[1] < unlike_pos_y+unlike_pos_height+5 and mouse_pos[1] > unlike_pos_y-5:
                                        continue
                                break
                title('小姐姐，我观察你很久了', screen, scale=[3, 8])
                title('做我女朋友好不好呀', screen, scale=[3, 4])
                button('好呀', like_pos_x, like_pos_y, like_pos_width, like_pos_height, like_color, screen)
                button('算了吧', unlike_pos_x, unlike_pos_y, unlike_pos_width, unlike_pos_height, unlike_color, screen)
                pygame.display.flip()
                pygame.display.update()
                clock.tick(60)
        show_like_interface('我就知道小姐姐你也喜欢我~', screen, color=(255, 0, 0))


if __name__ == '__main__':
        main()
```
在Excel中生成小姐姐，效果如下：

[![[v2-5a3498d90915b32d9cc5eafab35b7369_b.jpg]]
()

https://www.zhihu.com/video/1013058846654218240](https://link.zhihu.com/?target=https%3A//www.zhihu.com/video/1013058846654218240)介绍：

## 二. 可以写写爬虫为乐趣

比如写个音乐下载器：

![[v2-a93c8589b62be2843df7dfda67334896_720w.jpg]]
()

源代码：

[https://github.com/CharlesPikachu/musicdl](https://link.zhihu.com/?target=https%3A//github.com/CharlesPikachu/musicdl)

视频下载器：

![[v2-dd56ab299541c2918e3c901b822602f0_720w.jpg]]
()

源代码：

[CharlesPikachu/Video-Downloader](https://link.zhihu.com/?target=https%3A//github.com/CharlesPikachu/Video-Downloader)

分析分析知乎粉丝构成：

![[v2-aefc7380da8908c89d1b1cd4d79b2ae1_720w.jpg]]
()

![[v2-3665587c9ba7a65baeb7e62d0460d80f_720w.jpg]]
()

![[v2-78443fe44bbb6fd4017044911efc245e_720w.jpg]]
()

![[v2-50ecc4ab489fe7c165c1714453c192de_720w.jpg]]
()

## 三. 写写小游戏

比如坦克大战：

[![[v2-b956b1a8faadbb75b24f7d2583370f82.jpg]]
()

坦克大战https://www.zhihu.com/video/1188977395741372416](https://link.zhihu.com/?target=https%3A//www.zhihu.com/video/1188977395741372416)FlappyBird：

[![[v2-2132cdda2e30ca83978c87303acce060_b.jpg]]
()

https://www.zhihu.com/video/1013060715313315840](https://link.zhihu.com/?target=https%3A//www.zhihu.com/video/1013060715313315840)源代码：[CharlesPikachu/Games](https://link.zhihu.com/?target=https%3A//github.com/CharlesPikachu/Games)

***更多有趣好玩的Python项目：***

***[Charles：Python的一些小项目~不定期更新](https://zhuanlan.zhihu.com/p/33245706)***

***欢迎关注我的微信公众号：Charles的皮卡丘，不定期分享有趣好玩的Python项目以及大量的学习资源。***



---

经常有小伙伴私信问我我放的爬虫案例的代码实现细节/原理之类可不可以讲的更加详细一点，但是仔细一问，他们大多连最基础的爬虫相关的知识都不知道。对于这些小伙伴，建议大家从一些简单的爬虫案例开始学起。比如夜曲编程就推出过一个“python网络爬虫的课程”，课程内容设置十分丰富：

![[v2-de4177cc5732fca832bde3cd7a76330f_720w.jpg]]
()

![[v2-88dc8510921578a1e3a5d238a7781f51_720w.jpg]]
()

主要针对的是已经有一定python基础知识的小伙伴（没有的也不用担心哦，夜曲编程也提供了相关的python入门基础课呢～），每天下班后跟着课程内容学习大约40分钟，坚持一个月，差不多对大多数爬虫需求的代码实现信手拈来了。而且不同于网络上其他的视频和文本教程，夜曲编程还推出了助教在线答疑和社群讨论学习的功能，对于课程内容有疑问的小伙伴再也不用担心没人指导啦。

另外，我最喜欢的还是他们的课程奖励机制，帮助那些经常把资料放进收藏夹吃灰的小伙伴克服意志力不坚定的问题，按照要求完成课程的小伙伴可以得到触屏音箱等奖励呢～

***感兴趣的小伙伴可以关注一下他家的公主号“夜曲编程”，后台咨询具体的课程细节。注意，他家的课程都是可以开课三天内无条件退的哦，担心课程设置不适合自己的小伙伴完全可以先入手尝试几天，看看课程是否真的适合自己。也还有扎实的免费课可以拿，去咨询一回复下「免费课程」就行，虽然是免费的，但是也很充实。***





