### NameServer拆解

#### NamesrvController
##### 作用

该类的作用是作为rocketmq的服务注册逻辑控制器

##### 关键类属性ScheduledExecutorService


```Java
初始化方式： private final ScheduledExecutorService scheduledExecutorService = Executors.newSingleThreadScheduledExecutor(new ThreadFactoryImpl("NSScheduledThread"));
```

其作用定时对broker上报状态做同步状况检查，并将超过心跳同步时间的broker踢出集群

