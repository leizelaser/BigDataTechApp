# openMP的安装：
我们这里只说Ubuntu下通过bash的安装。
```
sudo apt-get install libomp-dev
```
后面编译时只需用类似
```
g++ -O3 xxx.c -fopenmp
```