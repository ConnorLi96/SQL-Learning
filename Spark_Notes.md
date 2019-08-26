## 安装
### spark
- pip install -i https://pypi.tuna.tsinghua.edu.cn/simple 使用镜像提升下载速度
- pyspark 常见路径 ```/home/work/.local/lib/python3.6/site-packages/pyspark/jars```
- pyspark --jars 'path' 初始化依赖 jar 包
- ```pip show```可以看到安装路径
- 然后把路径对应更改到 bash 文件夹里面
- bash 文件对应的只是一个 bash 窗口，其他的就不行

### jupyter notebook
- 一般情况下需要 notebook 做 IDE
- 可以不需要虚拟环境
- 需要设置密码以及配置文件
- 对应的 python 要和 spark一致
- jupyter notebook --generate config
- jupyter notebook password
- 然后更改配置文件
```
c.NotebookApp.ip='*'
c.NotebookApp.password = u'sha1:234c7b4ef8a7:cf707a23a01ae2e70289568cd3ef2b493815f29c'
c.NotebookApp.open_browser = True
c.NotebookApp.port =8888
```

## hive 
```spark.read.format('csv').options(header='true', inferschema ='true').option("delimiter", "\t").load('hdfs://hdp01.gridb.io:8020/user/hive/warehouse/spark_hive_test').show()```

```data.write.save('hdfs://hdp01.gridb.io:8020/user/hive/warehouse/save_test')```


成功搭建的环境变量：

```
SSH_CONNECTION=113.89.237.21 39709 172.31.40.179 22
LESSCLOSE=/usr/bin/lesspipe %s %s
LANG=C.UTF-8
S_COLORS=auto
XDG_SESSION_ID=59484
USER=work
GOPATH=/home/work/go
PWD=/home/work
HOME=/home/work
SSH_CLIENT=113.89.237.21 39709 22
XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
SSH_TTY=/dev/pts/0
MAIL=/var/mail/work
TERM=xterm-256color
SHELL=/bin/bash
SHLVL=1
LOGNAME=work
XDG_RUNTIME_DIR=/run/user/1001
PYSPARK_PYTHON=python3
PATH=/home/work/.local/bin:/home/work/bin:/home/work/go/bin:/home/work/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/local/go/bin:/snap/bin:/usr/local/go/bin
LESSOPEN=| /usr/bin/lesspipe %s
_=/usr/bin/env
```
