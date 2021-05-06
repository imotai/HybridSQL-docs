# 部署FEDB

## 部署zookeeper

建议部署3.4.14版本  
如果已有可用zookeeper集群可略过此步骤  

### 下载zookeeper安装包

```
wget https://archive.apache.org/dist/zookeeper/zookeeper-3.4.14/zookeeper-3.4.14.tar.gz
tar -zxvf zookeeper-3.4.14.tar.gz
cd zookeeper-3.4.14
cp conf/zoo_sample.cfg conf/zoo.cfg
```

### 修改配置文件

打开文件conf/zoo.cfg修改dataDir和clientPort

```
dataDir=./data
clientPort=2181
```

### 启动zookeeper

```
sh bin/zkServer.sh start
```

部署zookeeper集群[参考这里](https://zookeeper.apache.org/doc/r3.4.14/zookeeperStarted.html)

## fedb docker 部署

## fedb 单机部署

环境需要提前准备

如果是mac平台请选择mac包[fedb-2.2.0-mac.tar.gz](https://github.com/4paradigm/fedb/releases/download/2.2.0/fedb-2.2.0-mac.tar.gz),如果是linux请下载[fedb-2.2.0-linux.tar.gz](https://github.com/4paradigm/fedb/releases/download/2.2.0/fedb-2.2.0-linux.tar.gz)

### 启动fedb

fedb包含nameserver 和 tablet 可以执行相关脚本启动

#### mac 启动

```
tar -zxvf fedb-2.2.0-mac.tar.gz
cd fedb-2.2.0-mac
# 启动nameserver
./bin/start_ns.sh start
# 启动tablet
./bin/start.sh start
# 验证是否成功
./bin/fedb --zk_cluster=127.0.0.1:2181 --zk_root_path=/fedb --role=sql_client
# 如果打印一下信息，则表示成功
  ______   _____  ___
 |  ____|  |  __ \|  _ \
 | |__ ___ | |  | | |_) |
 |  __/ _  \ |  | |  _ <
 | | |  __ / |__| | |_) |
 |_|  \___||_____/|____/

v2.2.0.5056013c2.9284444a
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@753: Client environment:zookeeper.version=zookeeper C client 3.4.14
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@757: Client environment:host.name=wangtaizedeMacBook-Pro.local
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@764: Client environment:os.name=Darwin
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@765: Client environment:os.arch=20.4.0
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@766: Client environment:os.version=Darwin Kernel Version 20.4.0: Fri Mar  5 01:14:14 PST 2021; root:xnu-7195.101.1~3/RELEASE_X86_64
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@774: Client environment:user.name=wangtaize
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@782: Client environment:user.home=/Users/wangtaize
2021-05-06 17:25:34,283:11314(0x11454be00):ZOO_INFO@log_env@794: Client environment:user.dir=/Users/wangtaize/workspace/fedb_nb/fedb-2.2.0-mac
2021-05-06 17:25:34,283:11314(0x11454be00):ZOO_INFO@zookeeper_init@827: Initiating client connection, host=127.0.0.1:2181 sessionTimeout=2000 watcher=0x1025ed040 sessionId=0 sessionPasswd=<null> context=0x7f90d8008000 flags=0
2021-05-06 17:25:34,283:11314(0x700000886000):ZOO_INFO@check_events@1764: initiated connection to server [127.0.0.1:2181]
2021-05-06 17:25:34,284:11314(0x700000886000):ZOO_INFO@check_events@1811: session establishment complete on server [127.0.0.1:2181], sessionId=0x1000772a66f0002, negotiated timeout=4000
WARNING: Logging before InitGoogleLogging() is written to STDERR
I0506 17:25:34.284843 9474048 zk_client.cc:586] zookeeper event with type -1, state 3, path
I0506 17:25:34.284916 9474048 zk_client.cc:601] connect success
I0506 17:25:34.284934 341097984 cluster_sdk.cc:84] init zk client with zk cluster 127.0.0.1:2181 , zk path /fedb,session timeout 2000 and session id 1
I0506 17:25:34.285213 341097984 cluster_sdk.cc:254] no tables in db
I0506 17:25:34.289342 341097984 client_manager.cc:473] add client. name 127.0.0.1:9527, endpoint
I0506 17:25:34.289374 341097984 cluster_sdk.cc:102] start to watch table notify
I0506 17:25:34.290488 341097984 cluster_sdk.cc:134] init ns client with endpoint 127.0.0.1:6527 done
127.0.0.1:6527/>
```

#### linux 启动

```
tar -zxvf fedb-2.2.0-linux.tar.gz
cd fedb-2.2.0-linux
# 启动nameserver
./bin/start_ns.sh start
# 启动tablet
./bin/start.sh start
# 验证是否成功
./bin/fedb --zk_cluster=127.0.0.1:2181 --zk_root_path=/fedb --role=sql_client
# 如果打印一下信息，则表示成功
  ______   _____  ___
 |  ____|  |  __ \|  _ \
 | |__ ___ | |  | | |_) |
 |  __/ _  \ |  | |  _ <
 | | |  __ / |__| | |_) |
 |_|  \___||_____/|____/

v2.2.0.5056013c2.9284444a
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@753: Client environment:zookeeper.version=zookeeper C client 3.4.14
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@757: Client environment:host.name=wangtaizedeMacBook-Pro.local
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@764: Client environment:os.name=Darwin
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@765: Client environment:os.arch=20.4.0
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@766: Client environment:os.version=Darwin Kernel Version 20.4.0: Fri Mar  5 01:14:14 PST 2021; root:xnu-7195.101.1~3/RELEASE_X86_64
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@774: Client environment:user.name=wangtaize
2021-05-06 17:25:34,282:11314(0x11454be00):ZOO_INFO@log_env@782: Client environment:user.home=/Users/wangtaize
2021-05-06 17:25:34,283:11314(0x11454be00):ZOO_INFO@log_env@794: Client environment:user.dir=/Users/wangtaize/workspace/fedb_nb/fedb-2.2.0-mac
2021-05-06 17:25:34,283:11314(0x11454be00):ZOO_INFO@zookeeper_init@827: Initiating client connection, host=127.0.0.1:2181 sessionTimeout=2000 watcher=0x1025ed040 sessionId=0 sessionPasswd=<null> context=0x7f90d8008000 flags=0
2021-05-06 17:25:34,283:11314(0x700000886000):ZOO_INFO@check_events@1764: initiated connection to server [127.0.0.1:2181]
2021-05-06 17:25:34,284:11314(0x700000886000):ZOO_INFO@check_events@1811: session establishment complete on server [127.0.0.1:2181], sessionId=0x1000772a66f0002, negotiated timeout=4000
WARNING: Logging before InitGoogleLogging() is written to STDERR
I0506 17:25:34.284843 9474048 zk_client.cc:586] zookeeper event with type -1, state 3, path
I0506 17:25:34.284916 9474048 zk_client.cc:601] connect success
I0506 17:25:34.284934 341097984 cluster_sdk.cc:84] init zk client with zk cluster 127.0.0.1:2181 , zk path /fedb,session timeout 2000 and session id 1
I0506 17:25:34.285213 341097984 cluster_sdk.cc:254] no tables in db
I0506 17:25:34.289342 341097984 client_manager.cc:473] add client. name 127.0.0.1:9527, endpoint
I0506 17:25:34.289374 341097984 cluster_sdk.cc:102] start to watch table notify
I0506 17:25:34.290488 341097984 cluster_sdk.cc:134] init ns client with endpoint 127.0.0.1:6527 done
127.0.0.1:6527/>
```

## fedb 多节点部署

### 部署nameserver

#### 1 下载FEDB部署包

````
wget https://github.com/4paradigm/fedb/releases/download/2.2.0/fedb-2.2.0-linux.tar.gz
tar -zxvf fedb-2.2.0-linux.tar.gz
mv fedb-2.2.0 fedb-ns-2.2.0
cd fedb-ns-2.2.0
````

#### 2 修改配置文件conf/nameserver.flags

* 修改endpoint
* 修改zk_cluster为已经启动的zk集群地址. ip为zk所在机器的ip, port为zk配置文件中clientPort配置的端口号. 如果zk是集群模式用逗号分割, 格式为ip1:port1,ip2:port2,ip3:port3
* 如果和其他FEDB共用zk需要修改zk_root_path

```
--endpoint=172.27.128.31:6527
--role=nameserver
--zk_cluster=172.27.128.33:7181,172.27.128.32:7181,172.27.128.31:7181
--zk_root_path=/fedb_cluster
--enable_distsql=true
```

**注: endpoint不能用0.0.0.0和127.0.0.1**

#### 3 启动服务

```
sh bin/start_ns.sh start
```

### 部署tablet

#### 1 下载FEDB部署包

```
wget https://github.com/4paradigm/fedb/releases/download/2.2.0/fedb-2.2.0-linux.tar.gz
tar -zxvf fedb-2.2.0-linux.tar.gz
mv fedb-2.2.0 fedb-tablet-2.2.0
cd fedb-tablet-2.2.0
```

#### 2 修改配置文件conf/tablet.flags
* 修改endpoint
* 修改zk_cluster为已经启动的zk集群地址
* 如果和其他FEDB共用zk需要修改zk_root_path

```
--endpoint=172.27.128.33:9527
--role=tablet

# if tablet run as cluster mode zk_cluster and zk_root_path should be set
--zk_cluster=172.27.128.33:7181,172.27.128.32:7181,172.27.128.31:7181
--zk_root_path=/fedb_cluster
--enable_distsql=true
```

**注意：**
* endpoint不能用0.0.0.0和127.0.0.1 
* 如果此处使用的域名, 所有使用rtidb的client所在的机器都得配上对应的host. 不然会访问不到
* zk_cluster和zk_root_path配置和nameserver的保持一致

#### 3 启动服务

```
sh bin/start.sh start
```
**注: 服务启动后会在bin目录下产生tablet.pid文件, 里边保存启动时的进程号。如果该文件内的pid正在运行则会启动失败**

重复以上步骤部署多个nameserver和tablet
