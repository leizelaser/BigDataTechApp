# Python简单上手

强大的库，简单的语法，使得python成为当前最广泛学习的语言之一。同时具有命令行模式和脚本模式，使得测试检查都容易许多。

## 第一个程序：Hello, World!
```console
>>>> print("Hello, World!") # print command
```
脚本模式：把这行代码放入helloworld.py文件，在bash中运行：
```console
$ python helloworld.py
```

对比C的程序，一下区别
* 注释：以"#"开始，不参与编译
* 变量：在运算过程中，变量的类型可以灵活改变（更类似C意义下的指针，但又有固定内存）。
* 语句：以换行结尾，加";"也不影响
* 

### 变量类型详细解释

* Python中没有指针，但是把指针隐藏在了数组之中：这种做法在不明底层运作时尤其危险。
* list（列表）：[]，更类似集合，所有类型都可以放入其中。（但这种做法会使运算大幅减速。）
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
with f as open("test.txt","w+"):
    f.write("Hello world!")
    
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