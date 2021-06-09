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
rpc调用处理类
分为同步，和异步的调用，单向调用
同步和异步调用适用于消息事务
单向调用在无事务处理部分
```



