绪论

评估网站的性能	

- 用户角度
  - 访问站点一系列页面，直观的等待时间
  - 用户对站点的请求全部返回（页面、图片、css、js、iframe等），并成功渲染完毕
- 用户等待的时间里发生哪些事？
  - 数据在网络上传输的时间（也即响应时间），其决定因素是发送的数据量和网络带宽。
    - 浏览器主机发出请求数据经过网络达到服务器时间
    - 服务器回应数据经过网络会到浏览器主机时间
  - 站点服务器处理请求并返回数据的时间
    - 这部分时间主要消耗在服务器端，其中包括诸多环节，一般通过吞吐率（每秒处理请求数）。需要注意的是这里的吞吐率不是单位时间处理的数据量而是请求数。影响服务器吞吐率的因素非常多，例如：服务器并发策略、I／O模型、I／O性能、CPU数量（计算能力）以及应用自身的逻辑复杂度。
  - 浏览器本地计算和渲染的时间
    - 依赖因素：浏览器并发策略、样式渲染方式、脚本解释器性能（js解析性能）、页面大小及组件数量、组件缓存状况（此处组件指页面所需的各种资源）、页面组件域名分布以及DNS解析。

        综上可以看出，一个页面的等待时间包含了太多因素，如果有某处性能不佳，则整体速度可能受到影响。系统性能的瓶颈，一般就是影响性能的关键因素，而关键因素并不是一成不变的，会随着系统的运行不断的变化和迁移。例如，不同的用户及使用习惯，不同的时间段（例如电商网站的大促），又比如当数据存储量或者浏览量到达不同的级别时，瓶颈也会发生变化。

        除了系统的瓶颈，很多子因素也不可忽视。根据长尾效应的原理，如果对某个子因素进行了优化，也许性能上会有一定的提升，但不易被察觉，但是多个子因素的优化结果叠加在一起会带来性能上的显著提升。不过也要注意避免潜在的副作用。



常见的优化方案

增加带宽

##### 减少网页HTTP请求

##### 加快服务器脚本计算速度

##### 使用动态内容缓存(如何权衡缓存与某些数据实时交互的需求的矛盾？)

##### 使用数据缓存

##### 将动态内容静态化

##### 更换web服务器软件（不要过早下结论，很多情况下要跟实际场景来结合）

##### 页面组件分离（类似学校中的快慢分班）

##### 合理部署服务器（运营商、顶级交换节点、骨干线路）

##### 使用负载均衡(HTTP重定向、DNS轮询解析、反向代理、LVS)

##### 优化数据库(连接池、持久连接。关键点：如何根据Web站点的数据访问特点针对性地设置表的索引)

##### 考虑可扩展性（缺乏良好的扩展性的设计就像慢性自杀或者等待死亡）

##### 减少视觉等待

