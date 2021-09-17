## Bash 开启
* Ubuntu等linux系统的“终端”（terminal）就是bash，一般可以ctrl+alt+t快速唤起一个终端。
* IOS等基于unix系统的终端也是bash。
* windows10可以安装原生的ubuntu subsystem，不用模拟机进入bash，不会有硬盘不足的问题。但还处于实验阶段，以及无法唤起图形界面（意味着这个终端无法画图）。可以做简单练习但不建议在里面安装复杂软件。

## Ubuntu 下的设置

* Ubuntu下bash运行前会载入~/.bashrc和~/.bash_alias设置文件。这些尽量不要主动更改（除非对自己的修改很了解，例如添加指令链接等）。
* Ubuntu下有自己的软件库，一般通过 apt-get 指令进行安装，如
  ```console
  me@myPC:~$ sudo apt-get install vim
  ```
  以安装vim文字编辑软件。（python由于库依赖较多，不建议从此安装。）
  ubuntu自身会从官方的源寻找软件包，但是官方网站较慢，我们一般会寻找其他镜像。国内比较好的几个镜像是[清华](https://mirror.tuna.tsinghua.edu.cn/help/ubuntu/)、[科大](https://mirrors.ustc.edu.cn/help/ubuntu.html)等的。例如清华的源中显示：
  ```
  # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse

  # 预发布软件源，不建议启用
  # deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
  ```
  我们在终端中输入
  ```console
  me@myPC:~$ sudo gedit /etc/apt/sources.list
  ```
  /etc/apt/sources.list 文件就是源的地址信息，将其替换为上链接中文字（最好备份）后保存。之后更新设置：
  ```console
  me@myPC:~$ sudo apt-get update
  ```
  就可以继续用 apt-get 安装了。
* Ubuntu下的软件安装文件如果是.deb可以直接用自带的安装器安装。如果是.sh则需要先转变为可执行文件，用chmod指令；再直接运行.sh文件。
  例如Anaconda的安装程序就是.sh文件：
  ```console
  me@myPC:~$ chmod u+x ./Anaconda.sh
  me@myPC:~$ ./Anaconda.sh
  ```
  如果是压缩包(.tgz, .tar.gz)，大多不用安装，解压就可以运行（一般程序在bin文件夹下）。有些时候下载的是源代码可能需要cmake, python, java等程序编译，就较为复杂，需参考压缩包内的说明文档。