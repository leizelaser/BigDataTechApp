

运行pyspark
```
pyspark --master <master-url>
```

比如，要采用本地模式，在4个CPU核心上运行pyspark：
$ cd /usr/local/spark
$ ./bin/pyspark --master local[4]
或者，可以在CLASSPATH中添加code.jar，命令如下：
$ cd /usr/local/spark
$ ./bin/pyspark --master local[4] --jars code.jar
可以执行“spark-shell --help”命令，获取完整的选项列表，具体如下：
$ cd /usr/local/spark
$ ./bin/pyspark --help


javac WordCount.java -cp $(~/.../bin/hadoop classpath)