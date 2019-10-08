Arch Linux 安装  
===   
#### 1.下载镜像，制作U盘启动工具  
[Archlinux下载](https://www.archlinux.org/download/)  

下一步，把镜像写入U盘。  

这里推荐  

[Win32DiskImager](https://sourceforge.net/projects/win32diskimager/)   

[Win32DiskImager使用方法](https://jingyan.baidu.com/article/e5c39bf5eaf13639d7603385.html)  

[Rufus](http://rufus.ie/)  

[Rufus使用方法](https://jingyan.baidu.com/article/0a52e3f48ad2b8bf62ed7236.html)  

#### 2.开机进入U盘启动  

1.环境检查，区分UEFI与BIOS  

BIOS与UEFI不同，所以安装时有些步骤有差异，不确认清楚混用会导致Grub引导安装不成功。  

```bash
ls /sys/firmware/efi/efivars   #如果有很多行代码出现则是UEFI  

                               #若提示目录不存在则是BIOS   

```
#### 3.检查，连接网络
```bash
ping -c 3 www.baidu.com   #能ping通则忽略下一步WiFi连接  

```
```bash
wifi-menu  #选取WiFi进行连接  

```
然后是更新时间  

```bash
timedatectl set-ntp true
```
更换源，如果不还的话，网速感人，一二十kb每秒
```bash
nano /etc/pacman.d/mirrorlist #疯狂删，只留下China的地址
                              #不过，你也可以直接用F6搜索China
                              #方向键移动到这一行，Ctrl＋K剪切
                              #回到文件开头，然后把他Ctrl+U粘贴到
                              #Server之前，毕竟这个是按顺序来的
                              #Ctrl+O保存，确定，Ctrl+X退出
```
#### 4.分区
```bash
lsblk #检查一下自己的盘，确认自己想要安装的地方，
      #特别是你打算安装到移动硬盘上，一定要看清楚自己的盘的位置。
      #如果你是想安装在一整个盘上那没话说，如果你想装成双系统也行，
      #那你在分区时候注意一下好了，sda是第一个盘，sdb是第二个
      #sdX是第X个。而sda1表示第一个盘的第一个分区，以此类推
      #双系统要直接选定这个盘的某分区格式化，整个分区被占了。
```  
1.使用整个盘安装。  

```bash
cfdisk /dev/sdX #选定sdX进行分区，（使用的整块盘），
                #cfdisk有图形界面，所以推荐用他简化步骤
                #上下方向键选中，左右方向键，New，
                #然后输入第一个分区的大小，注意他提示的格式要求
                #然后是第二个分区home的方式与第一分区一样，
                #如果有swap分区记得，用左右方向键选择Type，
                #然后找到Linuxswap这个东西，确认。
                #最后对于UEFI环境必须建立EFI分区，
                #大小大概500M左右，并且选择Type为EFI system
                #根分区尽量大些，swap分区视情况而定，我一般4G
                #最后写入方向键到write，回车，然后输入yes，回车
```  
2.安装双系统  

```bash  
mkfs.btrfs -f /dev/sdXY #选取第X盘的第Y分区整个分区进行格式化

mount /dev/sdXY /mnt #挂载分区  
cd /mnt  

```
      





