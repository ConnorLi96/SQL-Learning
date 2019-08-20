## 安装
- ```pip show```可以看到安装路径
- 然后把路径对应更改到 bash 文件夹里面
- bash 文件对应的只是一个 bash 窗口，其他的就不行


## hive 
```spark.read.format('csv').options(header='true', inferschema ='true').option("delimiter", "\t").load('hdfs://hdp01.gridb.io:8020/user/hive/warehouse/spark_hive_test').show()```

```data.write.save('hdfs://hdp01.gridb.io:8020/user/hive/warehouse/save_test')```
