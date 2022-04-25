## 大数据科学与技术

### 历史：

> 2015年共有2个省级行政区的3所院校成功新增备案``数据科学与大数据技术``专业；  
> 2016年共有16个省级行政区的32所院校成功新增备案``数据科学与大数据技术``专业；  
> 2016年2月，北京大学为首家获批``数据科学与大数据技术``专业的高校，同时获批的还有对外经济贸易大学，中南大学；  
> 2017年共有29个省级行政区的250所院校成功新增备案``数据科学与大数据技术``专业；  
> 2017年3月，第二批32所高校获批``数据科学与大数据技术``专业；  
> 2018年共有28个省级行政区的196所院校成功新增备案``数据科学与大数据技术``专业；  
> 2018年3月，第三批250所高校获批``数据科学与大数据技术``专业；  
> 2019年全国29个省级行政区的481所院校成功新增备案``数据科学与大数据技术``专业；  
> 2019年3月，第四批196所高校获批``数据科学与大数据技术``专业；25所高校获批``大数据管理与应用``专业；35所高校获人工智能专业首批建设资格；  
> 2020年3月，138所高校获批第五批``数据科学与大数据技术``专业；180 所高校获批新增人工智能本科专业，开设人工智能专业的高校达到 215 所...  

分类：理科->工科
#### 本科课程设置(数学基础加计算机应用)：
* 公共与基础课程：40-46学分大学英语系列课程（2-8学分），政治系列课程（14学分），计算机系列课程（6学分），体育系列课程（4学分），数学分析(14学分)
* 核心课程：29学分高等代数Ⅰ(5学分)，高等代数Ⅱ（4学分），几何学（5学分），抽象代数（3学分），复变函数(3学分)，常微分方程（3学分），数学模型（3学分），概率论（3学分）
* 限选课程：32学分专业必选课程（6学分）：数理统计(3学分)，应用多元统计分析(3学分)
* 限选课程: 在下列课程中选修15学分实变函数（3学分）/实函与泛函（4学分），应用回归分析（3学分），贝叶斯理论与算法（3学分），应用时间序列分析（3学分），统计计算（3学分），统计机器学习（3学分），程序设计实习（3学分），数据结构与算法（3学分），分布与并行计算（3学分），算法设计与分析（3学分），数据库概论（3学分），自然语言处理导论（3学分），数值与计算方法（3学分），人工智能（3学分），最优化方法（3学分），深度学习（3学分），数据科学导论（3学分）

专业关键字：
* 数学、概率统计、计算理论：统计推断，优化理论->机器学习
* 计算技术：并行技术，分布式计算

常用工具：
* 编程：（基础到集成） C/C++ -> Python -> R, etc...
* 并行，分布式技术，数据处理框架：MP/Multi-Processing (OpenMP)，Message Passing Interface/MPI(OpenMPI, IntelMPI, mpich), CUDA(Nvidia-CUDA), MapReduce(Apache-Spark)

------

------

### 本课程目标
课程中每一部分（编程语言甚至编程库）都可以专门开一门课。此课程目的在于讲解了解科技发展现状，介绍这些技术的最基础用法，在未来科研/工作中遇到类似问题可以快速寻找解决方案。

### 本课程基础要求
* 计算概论：计算机组成，处理器内存工作基本原理，C或Python的简单编程

### 本课程大纲
#### 回顾：基本编程 
* Shell等[编程基础](https://github.com/missing-semester-cn/missing-semester-cn.github.io)
* C++: 内存，指针，类;
* python: [numpy](https://numpy.org), [numba](http://numba.pydata.org), [pandas](https://github.com/jvns/pandas-cookbook)

#### 多核并行式计算技术
* Message Passing Interface [MPI] (Ubuntu优先)
* [OpenMP] (Ubuntu优先)
* CUDA (类似Ubuntu的命令行优先，Visual Studio for Windows也可)

#### 分布式技术框架与数据/数据库结构
* 分布式数据结构：Hadoop (Ubuntu优先)
* Apache Spark (Ubuntu优先)

#### 其他
由于技术发展日新月异，今日的技术工具在明日就有了更好的优化替代（正如我们参考厦门大学林老师的教材，2013-2017-2020三版中每次都有大量增补）。本课程不设主要教材，除了基本的概念知识讲解以及练习，更重在锻炼学生自己的搜索学习能力，当未来遇到类似的软件类似的问题都可以主动寻找解决方案。
我们主要讲解重点放在几个基本常用软件，以及它们的基础设计；后续还会有更多更专门的软件（例如Flink流计算、Pregel图计算、D3可视化），我们仅简单介绍其应用场景与价值。

### 考核
本课程不准备设置纸质试卷，而以提交课程报告/做报告的形式进行考核评分。报告评分明细参考：

* 口头报告：
* 书面报告：




### 参考资料

* Ubuntu [官方网站](https://ubuntu.com) [下载桌面版](https://ubuntu.com/download/desktop)
* C++ [官方文档](https://www.cplusplus.com/reference/)
* python(3.x) [官方文档](https://docs.python.org/3/); Anaconda [官方网站](https://www.anaconda.com) [下载个人版](https://www.anaconda.com/products/individual)
------
* 数据库 [database]() [SQL]()
* [numpy](https://numpy.org), [numba](http://numba.pydata.org), [pandas](https://github.com/jvns/pandas-cookbook)
------
* [厦门大学计算机科学系 林子雨](http://dblab.xmu.edu.cn/)
* 林子雨 大数据技术原理与应用（第3版）[在线课程](http://www.icourse163.org/course/XMU-1002335004) [教材](http://dblab.xmu.edu.cn/post/bigdata3)
* 林子雨 Spark编程基础 Python版 [在线课程](https://www.bilibili.com/video/BV1oE411s7h7) [教材](http://dblab.xmu.edu.cn/post/spark-python/)
------
* MPI (Message Passing Interface) [官方网站，mpich](https://www.mpich.org/) [教程实例]()
* OpenMP [官方网站](https://www.openmp.org/) [教程实例]()
------
* Apache Hadoop [官方文档](https://hadoop.apache.org/docs/current/)
* Apache Spark [官方文档](http://spark.apache.org/docs/latest/) [官方示例](http://spark.apache.org/examples.html)
