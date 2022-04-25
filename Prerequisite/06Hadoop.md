# Hadoop的安装：
我们这里只说Ubuntu下通过bash的安装。参考[官方文档](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html)以及[官方下载链接](https://hadoop.apache.org/releases.html)，Windows版本的需要特殊途径安装，[参考](http://wiki.apache.org/hadoop/Hadoop2OnWindows)

1. 安装环境软件：
    1) [Java](https://cwiki.apache.org/confluence/display/HADOOP/Hadoop+Java+Versions)
    例如当前Java 8和Hadoop兼容，安装Java 8：
    ```
    sudo apt install openjdk-8-jdk
    ```
    安装结束后可以用：
    ```
    java -version
    ```
    检查版本信息。

    2) ssh 
    ```
    sudo apt-get install ssh
    sudo apt-get install pdsh
    ```
    安装后可以通过输入指令
    ```
    ssh localhost
    ```
    来测试是否可以建立本地连接。如果一定要设定密码才能建立安全连接的话，可执行以下代码：
    ```
    ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
    chmod 0600 ~/.ssh/authorized_keys
    ```
2. Hadoop主程序:
   从官方源中选取当前[稳定版本](https://archive.apache.org/dist/hadoop/common/stable/)。下载形如hadoop-x.x.x.tar.gz的文件（如hadoop-3.3.1.tar.gz），并解压至安装目标文件夹（例如下面选取的/opt/module/，注意/home/以外的文件夹多需要root权限。）
    ```
    sudo tar -zxvf hadoop-3.3.1.tar.gz -C /opt/module/
    ```
    为了配合Hadoop的后续使用，在etc/hadoop/hadoop-env.sh中定义下指令：
    ```
    # set to the root of your Java installation
    export JAVA_HOME=/usr/java/latest
    ```
    /usr/java/latest是java安装目录
    其中的/bin/hadoop就是主程序。可以将其指令添加至/home/.bash_alias便于操作。


# 设置伪分布式(Pseudo-Distributed Operation)
两个设置文件中相应地方修改：

etc/hadoop/core-site.xml:
```
<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>
</configuration>
```
etc/hadoop/hdfs-site.xml:
```
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```
同时需要保证ssh localhost可以免密码登录。

# 例：伪分布运行MapReduce指令
## 预先设置
ssh localhost 后执行：
格式化文件系统：
```
bin/hdfs namenode -format
```
开启伴随进程NameNode和DataNode:
```
sbin/start-dfs.sh
```
伴随进程日志写入$HADOOP_LOG_DIR directory文件夹(默认在$HADOOP_HOME/logs).
从网页端看NameNode; 默认在:
NameNode - http://localhost:9870/

建立HDFS文件夹，用于处理 MapReduce 的任务:

```
bin/hdfs dfs -mkdir /user
bin/hdfs dfs -mkdir /user/<username>
```

将文件复制到分布式文件系统中:
```
bin/hdfs dfs -mkdir input
bin/hdfs dfs -put etc/hadoop/*.xml input
```

跑示例程序：
```
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.1.jar grep input output 'dfs[a-z.]+'
```

将分布式文件系统中的结果文件复制出来:
```
bin/hdfs dfs -get output output
cat output/*
```
或者，直接在分布式文件系统中查看这些文件：
```
bin/hdfs dfs -cat output/*
```

使用完毕后，关闭相关进程：
```
sbin/stop-dfs.sh
```