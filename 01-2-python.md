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

# numpy库
numpy中最常见的类型是numpy.ndarray，多维数组类型。数组的直接运算要比for循环下的运算快很多。数组相关的常用函数有：
* numpy.array(): 从一个list或其他类型生成一个数组。
* numpy.zero(\[2,3\])：生成一个2 * 3的数组，元素都是0；类似的生成数组方法还有numpy.ones()。
* numpy.linspace(start, stop, num)：生成一个有num个元素，以start为首项，以stop为末项的等差数列。
* numpy.polyfit(x, y, deg)：将一维数组y用一维数组x的deg阶多项式拟合，得到各项前的系数。
后续我们会练习使用其他库。
------
# 练习：
目的是为了掌握常用计算、处理数据方法。如果不知道可以搜索括号里的关键字，在官方文档上找到示例。
1. 已知斐波那契数列前两项为1、1，用列表(list)输出前100项，和这一百项相邻两项比值，求这99个比值的平均数、标准差(numpy.mean, numpy.std)。
3. 将上斐波那契数列的第50至100项做线性拟合(numpy.polyfit)，求出斜率和截距。
5. 将上第50至100项的数据点和拟合直线绘图(matplotlib.pyplot)，用双对数坐标(log-log)展示。
4. 将斐波那契数列的和线性拟合的对应项的差输出至一数组，绘图并用双对数坐标(log-log)展示。
7. 将斐波那契数列前100项的数据保存至文本文件(numpy.savetxt)和二进制文件(pickle)。
