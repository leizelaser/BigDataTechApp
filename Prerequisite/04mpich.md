# mpich的安装：
我们这里只说Ubuntu下通过bash的安装。

从[官方网站](www.mpich.org/downloads/)下载mpich的安装包。
0. 在命令行安装gcc, g++, make和cmake
```
sudo apt-get install gcc
sudo apt-get install g++
sudo apt-get install make
sudo apt-get install cmake
```
1. 创建安装文件夹 将 mpich 安装到 /usr/mpich 文件夹（原则上任何文件夹都可以，方便后期管理可以安装到这里）
   将安装包复制到安装文件夹，并解压安装包（mpich-xxx.tar.gz代表压缩包名称）
```
sudo mkdir /usr/mpich
sudo cp  mpich-xxx.tar.gz    /usr/mpich
cd /usr/mpich
sudo tar -zxvf  mpich-xxx.tar.gz
```
2. 执行安装命令 
```
sudo ./configure --prefix=/usr/mpich
```
如果出错则根据报错来修改指令，直到出现"Configure completed"。
```
sudo make
sudo make install
```
3. 配置环境变量  （注意修改自己的路径）
```
sudo vim /etc/profile
```
在文件最后添加如下几行：
```
export PATH=/usr/mpich/bin:$PATH
export INCLUDE=/usr/mpich/include:$INCLUDE
export LD_LIBRARY_PATH=/usr/mpich/lib:$LD_LIBRARY_PATH
```
使用如下命令使配置文件生效:
```
source /etc/profile
```

测试配置是否成功,使用如下命令
```
which mpicc
```

后期可以使用mpicc(C程序)和mpiCC(C++程序来编译)