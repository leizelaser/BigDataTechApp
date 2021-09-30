# Python简单上手

以下官方文档的参考链接中有范例，安装后对应的库后可以自行测试学习：
* [Python官方文档] [2.x 已逐渐不再支持](https://docs.python.org/2/) [3.x](https://docs.python.org/3/)
* [numpy官方文档](https://numpy.org/doc/stable/index.html) 包括了数组矩阵的快速运算操作，拟合等多种
* [scipy官方文档](https://www.scipy.org/index.html) numpy的基础上增添了更多特殊函数和功能
* [sympy官方文档](https://www.sympy.org/en/index.html) python下的符号运算
* [numba官方文档](https://numba.pydata.org/) 高性能的python运算，和numpy、scipy等可以结合
* [matplotlib官方文档](https://matplotlib.org/stable/contents.html) 优质的2D、3D图表包
* [pandas官方文档](https://pandas.pydata.org/) python下的数据库处理包
* [pytorch官方文档](https://pytorch.org/) 2016年推出的开源Python机器学习库，有不输于tensorflow的性能

强大的库，简单的语法，使得python成为当前最广泛学习的语言之一。同时具有命令行模式和脚本模式，使得测试检查都容易许多。

## 第一个程序：Hello, World!
```console
>>>> print("Hello, World!") # print command
```
脚本模式：把这行代码放入helloworld.py文件，在bash中运行：
```console
$ python helloworld.py
```

对比C的程序，有以下区别：
* 注释：以"#"开始，不参与编译。
* 变量：在运算过程中，变量的类型可以灵活改变（更类似C意义下的指针，但又有固定内存）。
* 语句：以换行结尾，加";"也不影响。
* 程序结构：不需要主函数，代码会被一行一行执行，直到运行完毕或报错。

### 变量类型详细解释

* Python中没有指针，但是把指针隐藏在了数组之中：这种做法在不明底层运作时尤其危险。
* list（列表）：[]，更类似集合，所有类型都可以放入其中。（但这种做法会使运算大幅减速。）注意python中的角标计数从0开始。
* 对于纯数、字符的列表，可以使用数组。一般在numpy库中提供，用于统计计算。
* dict（字典）：使用hash地址，非线性存储，以一个"键"对应一个"值"（可以是列表，矩阵，各种类型）。其索引速度较快，有极小概率产生冲突。

## 判断、循环
不同于C需要花括号圈定语句的执行范围，python用首行缩进划工作范围，用判断、循环语句后加冒号：
* if, else, elif语句
```
if 2==3:
    print("false")
if True:
    print("true")
```
* for 语句
```
for i in range(0,10):
    if i%2 == 0:
        print("i")
```
* while 语句
```
a = 0
while(a<10):
    print(a)
    a += 1
```
* continue & break
```
a = 0
while(True):
    print(a)
    a+=1
    if (a==5):
        continue
    if (a==10):
        break
```
* with .. as 语句
一般多用于建立临时变量，在这个语句内有用。
例如文件的读写等命令常会使用这个语句。
```
with f as open("test.txt", "w+"):
    f.write("Hello world!")
```
    
## 函数

* 一般以def开始
```
def add(a,b):
    return a+b
print(add(3,4))
```
对于有简单返回值的，有很多简单的写法：
```
add(a,b) = a+b
add = lambda a,b:a+b
```

## 类和模块
和C++类似，python中也可以定义类，定义类的成员函数，类比*this*也有*self*来区分类的成员和其他变量。
模块则是对整片区域的一个规划。由于一般模块载入的路径是预设的，故无法简单编写模块。以上的numpy等软件库都是某块，类似C++中的标准库std。

下面我们说几个常见库：

# numpy库
numpy中最常见的类型是numpy.ndarray，多维数组类型。数组的直接运算要比for循环下的运算快很多。数组相关的常用函数有：
* numpy.array(): 从一个list或其他类型生成一个数组。
* numpy.zero(\[2,3\])：生成一个2 * 3的数组，元素都是0；类似的生成数组方法还有numpy.ones()。可以用于生成任意维度的数组（用于初始化）。
* numpy.linspace(start, stop, num)：生成一个有num个元素，以start为首项，以stop为末项的等差数列。
* numpy.polyfit(x, y, deg)：将一维数组y用一维数组x的deg阶多项式拟合，得到各项前的系数。
后续我们会练习使用其他库。

# matplotlib库
功能强大的绘图软件库，最常用的是其中绘制折线/散点/柱状图表的matplotlib.pyplot。（其他还可以绘制三维图标、三维曲面、二维色块等等，这里我们不详细说明）。
* matplotlib.pyplot.subplots 在图表中设置多个子图，返回值fig(ure)和ax(es)，我们更经常用ax。
* matplotlib.pyplot.plot / ax.plot (x, y, "b+", label="Data 1")，画x-y图像（x, y都是一维数组），"b+"是参数，表明画蓝色(b-lue)散点图，label在有图例的时候给出标识。
* ax.set_xlim, ax.set_xscale, ax.set_xlabel等：所有与坐标轴相关的设置，例如展示范围，对数坐标，或是坐标轴名称等，都可以用ax的相关函数进行设置。


------
# 练习：
目的是为了掌握常用计算、处理数据方法。如果不知道可以搜索括号里的关键字，在官方文档上找到示例。
1. 已知斐波那契数列（递推：第n项为第n-1项和第n-2项之和）前两项为1、1，用列表(list)输出前100项，和这一百项相邻两项比值，求这99个比值的平均数、标准差(numpy.mean, numpy.std)。
3. 将上斐波那契数列的第50至100项做线性拟合(numpy.polyfit)，求出斜率和截距。
5. 将上第50至100项的数据点和拟合直线绘图(matplotlib.pyplot)，用对数坐标(log)展示。
6. 将上第50至100项的数据点取对数后作线性拟合(numpy.polyfit)，求出斜率和截距，并给出斐波那契数列的近似表达式。
7. 将斐波那契数列的和对数线性拟合后重新取直属的对应项的差输出至一数组，绘图并用对数坐标展示。
8. 将斐波那契数列前100项的数据保存至文本文件(numpy.savetxt)和二进制文件(pickle)。