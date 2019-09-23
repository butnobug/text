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

在本地目录创建本地仓库，也可以新建文件夹，在里面右键git bash here
重新跳出bash窗口，，
```bash
git init         // 这时会有一个隐藏的.git文件夹在目录里（我是怎么知道的，当然是教程啦，以及我自己调了隐藏）
```
在该目录下创建一个代码或者复制粘贴过来到仓库里
然后 
```bash
git status      //出现红色的待添加到本地仓库的文件名字，还自动补了.txt后缀
git add 文件名.txt
```
然后把add的文件提交到仓库
```bash
git commit -m "备注"
```

讲本地仓库关联到GitHub上
```bash
git remote add origin http：//。。。。。。。。.git（之前复制的）
```
然后
```bash
git pull rebase origin master    //本地代码目录缺失README.md文件，完事后发现本地目录里有README.md了，
git push -u origin master   //创建仓库，提交代码，OK，
```

---------- 
[回到顶部](#readme)


