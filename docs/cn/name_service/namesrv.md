### NameServer拆解

#### NamesrvController
##### 作用

该类的作用是作为rocketmq的服务注册逻辑控制器

##### 关键类属性

##### ScheduledExecutorService

```Java
初始化方式： private final ScheduledExecutorService scheduledExecutorService = Executors.newSingleThreadScheduledExecutor(new ThreadFactoryImpl("NSScheduledThread"));
```

其作用定时对broker上报状态做同步状况检查，并将超过心跳同步时间的broker踢出集群

##### KVConfigManager

```java
关于topic的配置信息
```

##### NettyServerConfig

```te
netty默认配置信息类
```

##### RouteInfoManager

```
集群信息管理类。主要包含了topic，brokerName，clusterName，brokerAddr的元数据信息
```

##### RemotingServer

```wiki
用于与client端进行通讯
分为同步，和异步的调用，单向调用
同步和异步调用适用于消息事务
单向调用在无事务处理部分
```

##### BrokerHousekeepingService

```tex
处理与broker的通信事件（如链接关闭，链接关闭，链接异常，链接闲置等事件时）对应的处理方式
```

##### ExecutorService remotingExecutor

```tex
注册消息处理类运行线程池
```

##### FileWatchService 

###### 父类 [ServiceThread](../service_thread.md)

```tex
继承ServiceThread的文件监听类
```

