# 安装配置wsl2的Ubuntu  
## 前言  
对于我这个连**Linux**和**wsl**都没听说过的超级大萌新，在艰难（粗浅）的学习了git和markdown的使用之后，带着一脸焦糖色的死气，抱着一碗方便面，在凌晨一点的宿舍开启了这段艰辛的历程  
左看右看，上看下看，发现招新题目这没有给出操作教程（怒），于是我毅然决然点开kimi，在文本框里输入  
`安装wsl,使用wls2,在 Windows 环境下虚拟出一个带有完整 Linux 内核的开发环境`  
kimi刷刷刷的出现了教程，豪德，虽然什么都看不懂，但是我还是开始了！！！  
* 安装wsl 
* 安装Linux  
* 更新linux可视化界面 


## 这是一段艰辛的历程  
****
### 安装wsl  
这里有[wsl指令的含义](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands)，妈妈再也不用担心我看不懂指令啦
1. **启用虚拟机平台**
 >打开“控制面板” > “程序” > “启用或关闭Windows功能”。
 找到“虚拟机平台”，勾选它。
 点击“确定”，系统可能会要求您重启  

<img src="/1.png" width="50%">   

2. **启用wsl功能**  
>打开 PowerShell 作为管理员。
运行以下命令来启用 WSL 功能：  

``` 
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart  
   ```  
<img src="/2.png" width="80%">

3. **设置 WSL 2 为默认版本**
  > 打开 PowerShell 或 CMD 作为管理员。
   运行以下命令来设置 WSL 2 为默认版本：  

   `  wsl --set-default-version 2`  
![图片](/3.png)  
****
### 安装Linux  
1. **下载并安装 Linux 内核更新包**
> 访问 WSL2 Linux 内核更新包的[官方下载页面](https://aka.ms/wsl2kernel)。  
下载与您的系统架构匹配的更新包（x64 ）。
安装下载的更新包。  

![图片](/4.png)  

2. **从 Microsoft Store 安装 Linux 发行版**
  > 打开 Microsoft Store 应用，搜索linux，下载ubantu    

<img src="/14.png" width="50%">  


3. **配置发行版本**  
>首次启动时，将进行安装和配置过程，包括创建用户账户和密码  

**however，就在我跟着kimi教程走到这一步的时候，出现了错误**   
![图片](/6.png)
于是我把错误截图发送给kimi  
<img src="/7.png" width="60%">  
<img src="/8.png" width="60%"> 
我坚信不疑的跟着他的教程走，于是搞了一个多小时没有搞好  
我突发奇想，根据错误类型搜索对应的  [0x800701bc解决方案](https://zhuanlan.zhihu.com/p/599286889)
![picture](/9.png)    

>在wsl终端输入  

`wsl --update`  
![picture](/11.png)
豪德，当我重启启动ubantu的时候，马上就安装好了，好了现在我知道下一步该干什么了  
> 把kimi掐死    
4. **我们输入自己的用户名和密码**  
（忘记截图了0V0）应该是太激动了，忘记截图了！！！  
好了现在实在是太晚了，我熬不住了  

5. **睡觉**  
> 托拖鞋  
 盖被子  
> 闭上双眼  

<img src="/sleep.jpg" width="20%">

****
### 安装Linux可视化界面  
一觉睡醒，我胡三汉又回来了
看着这个命令行界面，寻思着我还要掌握各种命令才能使用Linux，在室友的推荐下我打算安装一个可视化界面  
由于kimi昨晚陪我熬夜，我今天早上觉得让他睡大觉，不去打扰他了  
  
1. **更新软件包列表**

>先后输入指令  

`sudo apt update`    
`sudo apt upgrade `   
<img src="/12.png" width="50%">  
<img src="/13.png" width="50%">   

2. **安装xfce4**  
>打开终端，在终端输入指令  

`sudo apt install xfce4`   
<img src="/install_xfc4.png" width="50%"> 
3. **查找ip地址**  
>在wsl终端输入指令
>找到WLAN一栏的ip4地址  
>复制保存好  

`ipconfig`  

4. **设置环境变量**  
>输入第一行指令  
>用鼠标滚轮下滑到最后一行  
>输入第二行指令之后，<kbd>ctrl</kbd>+<kbd>x</kbd> -> <kbd>y</kbd> -> <kbd>enter</kbd>退出
>输入第三行指令让修改生效

```
nano ~/.bashrc   
export DISPLAY=你的ip4地址:0   
source ~/.bashrc  
```    
<img src="/DISPLAY.png" width="80%">  

5. **安装vcxsrv**  
浏览器直接安装就好啦  
>打开桌面的程序  
选择
在extra settings一栏输入参数-ac  
save configuration选择在桌面
点击完成  

<img src="/large_windows.png" width="50%">
<img src="/ac.png" width="50%"> 


6. 打开可视化界面  
>记住指令，在终端输入即可打开可视化界面,输入设置好的程序  

`sudo startxfce4`  
![终端打开xfc4](/last_startxfce4.png)  
![可视化界面图](/victory.png)





  
****  
****
## 个人感想  
虽然我是一个**随和**的人，但是：
![picture](/10.png)  
我<u>急眼</u>了 (划重点)   
其实吧，在这个安装的过程其实是有很大收获的。**最重要的收获**就是，我学会了很多查找信息的渠道，从以前只会手机百度的我到现在利用kimi、文心一言,cdsn博客，知乎教程，B站视频，官方网站的自带教程，在edge的bing   等渠道来搜索想要的信息，极大拓展我的渠道。**其次**就是编写的第一个markdown文件和使用github创建个人远程库的过程，对于初学者来说我觉得并不是很简单的事情，尤其是在很多东西都看不懂的情况下，但是在自己慢慢摸索之下能够成功，其实是对我很大一种鼓励。**接着**，完成这些任务也是突破了我的眼界，从前以为程序员只是在各种编译软件上面敲代码，现在也是了解到更多行业相关的知识，感觉还是非常开心。

