# VirutalBox 简介
[VirtualBox](https://www.virtualbox.org/) 是一个较成熟的免费模拟机软件，可以在一个操作系统（host operating system）内“模拟”一个新的系统（guest operating system），而不用安装双系统。
优点：
* 不安装双系统，不设置引导，不用进行硬盘分区，不用通过开关机才能在两系统间切换。
* 模拟系统中也可以保证联网，进行复杂操作：例如windows中模拟ubuntu来运行ssh，ubuntu中模拟windows来编辑office文档。
缺点：
* 同时开两个系统，会同时拖慢两个系统，消耗更多资源。
* 鼠标键盘的位置不知会触发哪个系统的指令。

总体上模拟机已经很成熟，可以满足教学以及终端操作的需求。

* [官方说明文档](https://www.virtualbox.org/wiki/End-user_documentation)
* [官方下载链接](https://www.virtualbox.org/wiki/Downloads) 根据自己的系统选取合适的链接
  
## 安装最新稳定版的Ubuntu 20.04.3时，建议设置模拟硬盘20G以上(系统约10G)，内存2G以上。

## 安装过程：
详见[链接]()。简单说明如下



## 常用操作：

### 在模拟系统和原有系统中传输文件：
* 可以参考[共享剪贴板](https://blog.csdn.net/lyc_daniel/article/details/12613675?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0.no_search_link&spm=1001.2101.3001.4242)，可以直接使用复制粘贴，从文字到文件。
* 可以参考[共享文件夹](https://www.jianshu.com/p/5b66e1ec09dc)，建立共享文件夹以便于传输。
  每次在虚拟机内ubuntu下使用共享文件夹前需要挂载，在终端中执行以下命令：
  ```
  sudo mkdir /mnt/shared
  sudo mount -t vboxsf sharewin /mnt/shared
  ```
  "sharewin"是Windows下的共享文件夹名字，每次从Ubuntu的"/mnt/shared"地址进入共享文件夹。
  
## 常见安装问题：
* 报错内容和没有权限(Authorization)相关: 多因为安装的文件目录受保护。用管理员模式运行VirtualBox即可。
* 报错内容和BIOS/Virtualization/v-x等名称相关：多因为BIOS上禁止了虚拟机运行。需要在启动时进入BIOS菜单更改设定。（具体进入BIOS的方法，以及更改设定的目录因机型而定，需上网搜索。大多是开机时按F9到F12中的某一个键。）
* 需检验下载安装镜像的完整性。一般下载文件目录会提供SHA1Sum等校验码，提供下载完成后的对比检验。如果对比不一致说明下载有损坏/未完成，需重新下载。
* 报错内容和缺少某些.dll文件相关：用管理员模式，简化路径（避免中文和特殊字符），尝试重新安装VirtualBox。
