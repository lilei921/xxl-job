1、QRTZ_JOB_DETAILS：存储的是job的详细信息，
    包括：[DESCRIPTION]描述，[IS_DURABLE]是否持久化，[JOB_DATA]持久化对象等基本信息。

2、QRTZ_TRIGGERS：触发器信息,
    包含：job的名，组外键，[DESCRIPTION]触发器的描述等基本信息，
    还有[START_TIME]开始执行时间，[END_TIME]结束执行时间，[PREV_FIRE_TIME]上次执行时间，
    [NEXT_FIRE_TIME]下次执行时间，[TRIGGER_TYPE]触发器类型：simple和cron，
    [TRIGGER_STATE]执行状态：WAITING，PAUSED，ACQUIRED分别为：等待，暂停，运行中。

3、QRTZ_CRON_TRIGGERS：保存cron表达式。

4、QRTZ_SCHEDULER_STATE：存储集群中note实例信息，quartz会定时读取该表的信息判断集群中每个实例的当前状态，
    INSTANCE_NAME:之前配置文件中org.quartz.scheduler.instanceId配置的名字，就会写入该字段，
    如果设置为AUTO,quartz会根据物理机名和当前时间产生一个名字。  [LAST_CHECKIN_TIME]上次检查时间，[CHECKIN_INTERVAL]检查间隔时间。

5、QRTZ_PAUSED_TRIGGER_GRPS：暂停的任务组信息。

6、QRTZ_LOCKS，悲观锁发生的记录信息。

7、QRTZ_FIRED_TRIGGERS，正在运行的触发器信息。

8、QRTZ_SIMPLE_TRIGGERS，简单的出发器详细信息。

9、QRTZ_BLOB_TRIGGERS,触发器存为二进制大对象类型(用于Quartz用户自己触发数据库定制自己的触发器，然而JobStore不明白怎么存放实例的时候)。