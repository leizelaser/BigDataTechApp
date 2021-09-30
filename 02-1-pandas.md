# pandas简单上手
本文参考[Pandas cookbook](https://github.com/jvns/pandas-cookbook)和[pandas官方文档](https://pandas.pydata.org/)

pandas是python中一个数据处理的库，可以执行（而且已经很优化）的操作有：
* 从数据文件(.csv，.sql)中读取信息
* 选取某一行信息，进行某种修改
* 选取某一列信息，进行某种操作（统计）
* 将多组数据(dataframe)组合
* 字符操作，字符检索

pandas中最常用的数据类是DataFrame（可以类比numpy中的ndarray，其结构和R中类似），可以从字典、数组中建立数据表格。
Series（一维数据）与DataFrame（二维数据），
在python中载入pandas库：
```
import pandas
```

## [读取信息](https://pandas.pydata.org/docs/pandas.pdf#section.2.4)：
支持的文件类型格式有很多，包括SAS和SPSS软件的文件格式（读）甚至分布式中经常使用的HDF5（读写）。我们只用csv（读写）和sql（读）举例说明。
### 从csv文件中读取信息：
csv文件多是2维表格，每行以逗号分割项目，结尾回车以换下一个数据。

```
df = pandas.read_csv(csv_filename, sep=';', encoding='latin1', parse_dates=['Date'], dayfirst=True, index_col='Date')
```
comptage_velo_2021
read_csv命令第一个参数是csv文件路径/数据缓冲，后面都是更详细的设置：用分号分割、用拉丁字符编码，重新整理'Date'栏名称，用欧式日期风格(dd/mm/yy)，给列命名。我们可以先读取文件后，再进行更详细的设置。

将dataframe输出至csv，格式和read_csv相似，也可以加更详细的设置内容：
```
df.to_csv(savefile_name)
```

### 从sql文件中读取信息：
sql大多是二进制索引文件，我们直接难以看出，但借助python-pandas可以将文件信息读入内存。

示例使用了SQLite类型，需要sqlite3库支持。但更一般的MySQL等类型也可以类似处理（MySQLdb库）。
```
import pandas
import sqlite3
```

```
import MySQLdb
con = MySQLdb.connect(host="localhost", db="test") 
```
参数为主机名称和数据库名称。读取文件时用read_sql指令即可。
```
df_mysql = pandas.read_sql('select * from VIEWS;', con=con)  
```
'select * from VIEWS;'是SQL中选取VIEWS下的所有数据的指令；对于更一般地SQL操作，在第一条命令中输入合适的字符串即可完成。

### 写成excel输出：
```
df.to_excel('test.xlsx')
```
------
下来我们来借助DataFrame格式完成一些数据操作：

##