



## URL

ed2k://|file|cn\_office\_professional\_plus\_2019\_x86\_x64\_dvd\_5e5be643.iso|3775004672|1E4FFA5240F21F60DC027F73F1C62FF4|/

* 用迅雷（或者其他下载工具）使用上面链接下载office 2019
* 上面链接来源于：[MSDN, 我告诉你 - 做一个安静的工具站](https://link.zhihu.com/?target=https%3A//msdn.itellyou.cn/)，网站作者收集的软件包都是来自官方原版软件收录（作者是这么申明的）,**干货网站你值得拥有**；

## 联网激活


```
@echo off
(cd /d "%~dp0")&&(NET FILE||(powershell start-process -FilePath '%0' -verb runas)&&(exit /B)) >NUL 2>&1
title Office 2019 Activator r/Piracy
echo Converting... & mode 40,25
(if exist "%ProgramFiles%\Microsoft Office\Office16\ospp.vbs" cd /d "%ProgramFiles%\Microsoft Office\Office16")&(if exist "%ProgramFiles(x86)%\Microsoft Office\Office16\ospp.vbs" cd /d "%ProgramFiles(x86)%\Microsoft Office\Office16")&(for /f %%x in ('dir /b ..\root\Licenses16\ProPlus2019VL*.xrm-ms') do cscript ospp.vbs /inslic:"..\root\Licenses16\%%x" >nul)&(for /f %%x in ('dir /b ..\root\Licenses16\ProPlus2019VL*.xrm-ms') do cscript ospp.vbs /inslic:"..\root\Licenses16\%%x" >nul)
cscript //nologo ospp.vbs /unpkey:6MWKP >nul&cscript //nologo ospp.vbs /inpkey:NMMKJ-6RK4F-KMJVX-8D9MJ-6MWKP >nul&set i=1
:server
if %i%==1 set KMS_Sev=kms7.MSGuides.com
if %i%==2 set KMS_Sev=kms8.MSGuides.com
if %i%==3 set KMS_Sev=kms9.MSGuides.com
cscript //nologo ospp.vbs /sethst:%KMS_Sev% >nul
echo %KMS_Sev% & echo Activating...
cscript //nologo ospp.vbs /act | find /i "successful" && (echo Complete) || (echo Trying another KMS Server & set /a i+=1 & goto server)
pause >nul
exit
```
* 把上面这段代码保存到txt，把扩展名.txt改成.bat，office安装好了右键点击**以管理员身份运行**运行这个bat；
* 激活成功提示 大约1~3分钟界面提示**Product activation successful**和**Complete**，表示激活成功；
* 以上是使用KMS联网激活，激活时长为180天，如果使用后某天发现激活失效了，就重新按上面方法运行一下bat再激活；

**感谢关注！**





