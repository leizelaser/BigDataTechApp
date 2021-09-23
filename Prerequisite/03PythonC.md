# Python

Linux和Windows版可以从Anaconda安装。
## 运行Python
安装完毕后指令行（Ubuntu: bash terminal; Windows: cmd, powershell）输python可运行，另外还有spyder, jupyter notebook等IDE辅助编辑。

## 环境的选择和额外库的安装
如果我们想在某些情况下使用一些库，另一些情况下不用它们而用其他的库（多种库中可能有冲突）；或者我们需要使用旧版本的软件和库，这时我们就需要创建环境，选择环境以及挑选某一环境下的库

* Windows下打开Anaconda Navigator，左侧选择Environments，对应中间列表有现有的环境（可以创建），右侧是有的库，搜索后直接勾选以安装。base(root)下安装了所有的库。
* linux下[详见](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)。
  打开terminal，输入
  ```
  conda create --name myenv
  ```
  以创建名为"myenv"的环境。
  激活此环境：
  ```
  conda activate myenv
  ```
  取消激活：
  ```
  conda deactivate
  ```
  在其中安装scipy的库（如不加-n myenv则安装在base里）：
  ```
  conda install -n myenv scipy
  ```

# C、C++

## Ubuntu
可以用apt-get安装g++。
```console
me@myPC:~$ sudo apt-get install g++
```

## Windows
Windows可以使用[Visual Studio](https://visualstudio.microsoft.com/zh-hans/)，传统的Windows下C++编写编译工具。随着版本更新，其内容也越来越充实，增加了许多其他编程语言如C#、python等。Community版本即可供一般人员正常编译代码。
注意：Visual Studio Code只是一款编辑软件（IDE），不具有编译功能；但可以和编译器结合使用。
Visual Studio的操作大多不用命令行而用图形界面，[参考](https://visualstudio.microsoft.com/zh-hans/vs/getting-started/#cplusplus)。

Windows 下也可以安装[mingw](https://www.mingw-w64.org/)，[下载链接](http://win-builds.org/doku.php/download_and_installation_from_windows)。安装好后在powershell中可以和Linux一样运行g++编译c++代码。
