任务报告
===
1.    git是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。git是一种工具，它能更好的让我们管理代码。很多时候如果我们需要保持本地代码和github代码版本一致，就会用到git这个工具。

2. 账号注册略。（老久以前注册的，咱也没重新注册）
然后，创建一个仓库。create respository，完事后复制一下网页地址。
下载安装git，（我的）其中的基本按照默认，勾一下创建快捷方式即可。
安装完事后，有一个git bash，开启，一个黑框框，查教程开始了
   我知道要先在本地创建一个ssh key，在窗口键入 
```bash
ssh-keygen -t rsa -C "3047927842@qq.com" 
```
 然后一路回车，要设密码可以设，
 然后按照窗口里的目录用记事本打开id_rsa文件（有两个同名的，找.pub后缀名的,我哪里没有这个后缀名，但是对文件类型有区分，一个类型为文件，另一个是微软啥  啥啥的，看图标就知道是文档类）打开后，全部复制，
 到浏览器界面，右上角的小三角形点开，setting，找到SSH and GPG keys，第一个描述一下是哪一个机器的，下一个框粘贴内容即可，最后ADD.
 然后检查是否绑定成功
 ```bash
 ssh  -T git@github.com
 ```
然后yes 回车  
输入代码提交者信息
```bash
git config --global user.name "用户名" 
git config --global user.email "3047927842@qq.com"
```  
关联远程仓库  
```bash
git remote add origin git@github.com:3047927842/text.git  
```
```bash
git clone https://github,com/3047927842/text.git    //为保证本地库文件中有README.md
```  
  
打开他把文件移动过来，或者创建一个文件
然后重新定位git的位置，定位在库的文件夹内  
```bash  
ls  //查看新创建的文件
```  
```bash
git status      //出现红色的待添加到本地仓库的文件名字，还自动补了.txt后缀
git add 文件名.txt
```
```bash  
git add 文件名称（带后缀)  //将文件add到Index 缓存区
git commit -m "对文件的描述"   //commit 将文件送入HEAD，但是仍未进入远端仓库
git push origin master    //将改动提交到远端仓库，master可以换成想要推送的其他分支  
```  


---------- 
[回到顶部](#readme)


