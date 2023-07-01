



对于没有自备梯子的用户，由于无法连接 Google 服务器，在使用 Chrome 时都面临不少问题：  


* Chrome 浏览器更新总是出现「检查更新时出错」；
* 看到好用的扩展但是无法下载；
* 不同设备之间的 Chrome 浏览器无法同步个人数据。

所以不少人转而使用国内厂商开发的软件管家之类工具，或者直接选择常年不更新，或者放弃使用了 Chrome 浏览器。

那么，我为大家准备了这样一份 Chrome 使用指南，「曲线救国」实现顺畅使用 Chrome 浏览器、扩展和数据同步的目的，带大家告别「常年不更新、不同步、不备份 Chrome」的尴尬难题。 

## 哪里能找到靠谱的 Chrome 离线安装包？

推荐两个在线网站服务：[浏览迷](https://link.zhihu.com/?target=https%3A//liulanmi.com/)、[getchrome 下载地址查询服务](https://link.zhihu.com/?target=https%3A//api.shuax.com/tools/getchrome)，其中「浏览迷」会及时跟进 Chrome 浏览器正式版的更新内容，其中报道文章会有浏览器版本更新的内容和下载地址，网站给出的下载地址均为可直接下载的真实地址，同时网站还有一个 [小工具](https://link.zhihu.com/?target=https%3A//liulanmi.com/labs/core.html) 就是 Chrome 内核浏览器内核及版本检测，定期在线检测一下你的浏览器正式版是不是最新版本。

而「getchrome 下载地址查询服务」相当适合尝鲜用户，网站最主要的作用就是定时检测 Chrome 是否有更新，已经覆盖了 Stable、Beta、Dev、Canary 更新通道以及 32/64 位版本，号称提供了 Google 官方离线包，建议大家对照自己电脑安装的版本选择 https 的下载链接，并且网站提供了每一个版本号、文件大小、查询时间、SHA1、SHA256 认证。

![[v2-2363dfd8dd804c24913a9b48ef2db2b5_720w.jpg]]
()

## 除了 Chrome 商店还有哪能下载扩展？

Chrome 最大的特色之一就是其支持大量的扩展程序，[Chrome 网上应用商店](https://link.zhihu.com/?target=https%3A//chrome.google.com/webstore/category/extensions) 是目前唯一的官方分发渠道，但不少用户由于并不理想的网络环境，无法通过官方渠道下载 Chrome 扩展，推荐一个第三方的 Chrome 扩展网站：[Crx4Chrome](https://link.zhihu.com/?target=https%3A//www.crx4chrome.com/)。

与官方商店相比，Crx4Chrome 给出的数据信息更加全面，热门扩展排行、热门应用排行、最新扩展等不同形式的排行榜，帮助用户发现自己需要的 Chrome 扩展。

在这里，为大家补充如何通过 Crx4Chrome 下载扩展和安装扩展。

**方法一：**

1. 通过搜索找到需要的扩展，介绍页面中提供了 Crx4Chrome 下载地址或者外链至 Chrome Store 官方商店，大家也可以看到扩展的的运行截图、功能介绍、评分、下载总数的信息；

2. 点击扩展介绍页面中的「Install」之后，就会自动转到下载页面，Crx4Chrome 提供了多个下载源，推荐大家下载 Crx4Chrome 提供的官方源，下载后会得到 .crx 格式的文件；

![[v2-8cc6ded2cf00f269040bd5f0411d27dd_720w.jpg]]
()

3. 打开 Chrome，输入网址 chrome://extensions/ 或者点击右上角的目录图标，设置 - 更多工具 - 扩展程序，把刚才下载的 crx 格式文件拖拽到扩展程序界面，这时会提示安装。

![[v2-8b1f664420577545acc82f123d4139e1_720w.jpg]]
()

**方法二：**

1. 在方法一第二步中，将 .crx 文件的扩展名改为 .rar 或 .zip，然后解压；

2. 在 Chrome 地址栏输入 chrome://extensions/，勾选「开发者模式」，点击「加载已解压的扩展程序」，选择上一个步骤解压出来的扩展所在文件夹。如果出现加载扩展程序时出错，将解压文件中的 \_metadata 文件夹的名字修改为 metadata（即把下划线去掉）。

![[v2-b35cd854e4fdfc8678b4be54b7df62e6_720w.jpg]]
()

## 怎么在本地备份和恢复已经装好的 Chrome 扩展？

## 备份扩展

1. Chrome 地址栏输入 chrome://extensions/ 选择开发者模式后，单击**打包扩展程序**，可以看到一个**扩展程序根目录**输入框页面；

![[v2-287fa34f3552ac945deba0aff31d58d9_720w.jpg]]
()

2. 进入入 C:/Users//AppDataLocal/GoogleChrome/User Data/Default/Extensions (<username>是电脑的用户名称)目录下，会看到许多以 id 号命名的文件夹，这些文件夹就是 Chrome 安装的扩展，进入 id 目录，会看到一个版本号目录。如下：


```
C:/Users/<username>/AppDataLocal/GoogleChrome/User Data/Default/Extensions/aapbdbdomjkkjkaonfhkkikfgjllcleb2.0.6_0
```
![[v2-644a6926b87d8a9e14ddc9124ede48d8_720w.jpg]]
()

3. 复制第二步的**版本号目录文件路径**到第一步中弹出输入框页面的扩展**程序根目录**,点击**打包扩展**的按钮，就可以在 id 目录下找到对应的 .crx 格式扩展和密钥文件。同理，把所有的 id (即 Chrome 扩展)手动备份。  


![[v2-62b23b74428429b9a981786323dd82b4_720w.jpg]]
()

## 恢复已备份的扩展

恢复扩展这部分与上面介绍通过 Crx4Chrome 下载扩展和安装扩展的部分保持一致，大家可以在chrome://extensions/扩展页面，点击「加载已解压的扩展程序」或者拖拽 .crx 文件手动进行扩展安装恢复。

## 怎么在本地备份书签 & 个人设置？

## 备份书签

Chrome 本身已经提供了书签导出导入功能，在浏览器地址栏输入网址 chrome://bookmarks/或者打开设置 - 书签 - 书签管理器，可对书签以 HTML 文件进行导入或者导出的操作，再配合云端存储服务，可方便实现书签跨平台、跨设备保存和同步。

![[v2-4e8aa2963003d06060481a314d485546_720w.jpg]]
()

如果喜欢可视化书签管理的话，可安装扩展 [Speed dial 2](https://link.zhihu.com/?target=https%3A//chrome.google.com/webstore/detail/speed-dial-2-new-tab/jpfpebmajhhopeonhlcgidhclcccjcik%3Futm_source%3Dchrome-app-launcher-info-dialog)，提供了可视化书签、数据统计打开网站习惯，甚至还有 Speed Dial 2 帐户体系，方便云端同步。

![[v2-217c8222d583f1b046b2b6009435e6c1_720w.jpg]]
()

## 备份个人文件

诚然，Chrome 自家的同步功能是最为全面，可同步的数据类型包括了应用、自动填充、书签、扩展程序、历史记录、密码、设置、主题背景和壁纸、打开的标签页、Google Payments 中存储的信用卡和地址信息。

目前，用户手动备份个人文件的具体操作：

1. 在 Chrome 地址栏输入 chrome://version/，回车键进入页面，大家可以看到当前浏览器的相关信息，重点就是**个人资料路径**显示的文件路径。

![[v2-5b587330c7cc3ffa330909b036ee3575_720w.jpg]]
()

2. 复制第一步的**个人资料路径**，在本地随意一个文件夹窗口的地址栏粘贴并打开上面的地址，将会看到大量 Chrome 浏览器产生的文件夹和文件。默认的 Chrome 的配置文件夹被直接命名为 Default，完整的路径类似：C:/Users/<username>/AppDataLocal/GoogleChrome/User Data/Default

如果用户创建了多个 Chrome 用户的话，则会有额外的配置文件，将以 Profile N （N 代表从 1 开始的数字）的方式来对配置文件夹命名。

![[v2-ff353a5e44c8efd04af26c0b75bafab5_720w.jpg]]
()

3. 备份方式很简单，重装系统之前将目录拷贝出来，重装系统之后再将目录恢复回去就可以了。

## 怎么查看和备份 Chrome 保存的密码？

用户每次登陆某个网站服务的时候，Chrome 都会提示是否保存密码，方便以后登陆的时候不再需要手动填写用户名、密码。**如何查看 Chrome 保存过的密码？**

在 Chrome 地址栏输入 chrome://settings-frame/passwords 回车打开密码页面，页面显示了已保存的密码和一律不保存的网站列表，点击其中保存密码的网站，会有**显示**的按钮，点击之后会弹出请输入电脑系统本身设置好的密码（为了安全起，建议大家设置系统的用户账号密码），即可直接看到密码。

![[v2-3242647c3a6cb1474a5e2ddfa54e9034_720w.jpg]]
()

## 导出和导入密码

1. Chrome 地址栏输入 chrome://flags/#password-import-export，打开页面

2. 显示位置会自动定位到「Password import and export」选项，默认状态是 Default，手动选择 Enabled，Chrome 将会自动提示更改会在重新启动浏览器时生效，点击立即重新启动。  


![[v2-faf850e0972689d065807218905aa177_720w.jpg]]
()

3. 回到前面提到的 chrome://settings-frame/passwords 密码页面，新增了导入和导出选项。Chrome 将以 .csv 格式文件导出密码信息，内容包括了 name、url、usename、password。

![[v2-bf01a01bb84ee23128a8ccd3bbb14e75_720w.jpg]]
()

## 第三方查看备份密码的工具

第三方工具 [ChromePass](https://link.zhihu.com/?target=http%3A//www.nirsoft.net/utils/chromepass.html) 可以让用户查看 Chrome （对 Firefox、 Vivaldi 等浏览器同样有效）已存储的用户名称和密码，这款工具会显示出以下信息：来源地址（Origin URL）、生效地址（Action URL）、用户名称字段、密码字段、用户名称、密码、密码强度、密码创建时间以及密码保存的文件路径。

我们可以选择一个后者多个项目，选择以 txt、html、xml 格式文件或者直接复制到剪贴板上，即可完成对 Chrome 存储密码的查看和备份工作。与 Chrome 浏览器本身查看密码时需要输入系统管理员密码不同，ChromePass 支持直接显示密码内容。  


![[v2-70389b58499e9c5e70c3611909788308_720w.jpg]]
()

希望这份使用指南帮助「守法公民」做好各种 Chrome 数据类型的查看和备份工作。当面临不同平台和设备之间的数据同步、Chrome 新版安装包如何下载的难题时，透过这篇文章大家都可以从容应付。





