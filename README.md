# 封装1个实用的线程池库ThreadPoolUtils 
## 根据任务不同type类型建立不同的线程池：
1.CPU密集型 =>corePoolSize=CPU数量 + 1【使用ThreadPoolExecutor自定义线程池】  
2.IO密集型 =>corePoolSize=CPU数量 * CPU利用率 * (1 + 线程等待时间/线程CPU时间)【使用ThreadPoolExecutor自定义线程池】
3.耗电型 =>JobScheduler处理不紧急的任务，省电
## 封装线程池的可以支持的功能如下：														
1.支持Callable和Runnable 2种callback
2.支持postdelay
3.支持串行（类似AsynkTask）
4.支持并行（类似newCachedExecutor）
5.支持设置任务优先级
6.支持查询正在等待执行的任务:ThreadPoolUtils.getWaitingJobsByTag(String tag)	
7.支持JobScheduler

代码实现还在开发中，暂时可参考 https://github.com/yangchong211/YCThreadPool/releases/tag/1.3.8
