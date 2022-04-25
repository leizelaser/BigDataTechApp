# Spark的安装：
我们这里只说Ubuntu下通过bash的安装。参考[官方文档](http://spark.apache.org/docs/latest/)
Spark要配合Hadoop使用，所以我们默认已经有完整安装的Hadoop软件。注意从[下载链接](https://link.zhihu.com/?target=https%3A//spark.apache.org/downloads.html)安装和已有Hadoop版本相配的Spark。

解压压缩包
```
sudo tar -zxvf spark-3.1.2-bin-hadoop3.2.tgz
```
其中./bin文件夹内就是所有可执行程序，包括pyspark, spark-shell, sparkR等用不同语言写成的spark。但需要使用这些还需要预先配置。
以python为例，我们需要numpy，pandas等支持，所以需要在有Anaconda的情况下继续安装。

配置文件：
conf/spark-env.sh
需要设置环境变量：
JAVA_HOME
SCALA_HOME
HADOOP_HOME
以及
SPARK_HOME

