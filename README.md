## 基于seata + dubbo的分布式事务--- AT模式和TCC模式实战



在微服务开发中，存在诸多的开发痛点，例如分布式事务、全链路跟踪、限流降级和服务平滑上下线等。而在这其中，分布式事务是最让开发者头痛的。那分布式事务是什么呢？

![](https://james-1258744956.cos.ap-shanghai.myqcloud.com/%E5%BE%AE%E6%9C%8D%E5%8A%A1%E6%9C%80%E5%A4%A7%E7%9A%84%E5%BC%80%E5%8F%91%E7%97%9B%E7%82%B9-%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1SEATA%E5%85%A5%E9%97%A8%E7%AE%80%E4%BB%8B/%E5%BE%AE%E6%9C%8D%E5%8A%A1%E5%BC%80%E5%8F%91%E7%97%9B%E7%82%B9.png)

分布式事务就是指事务的参与者、支持事务的服务器、资源服务器以及事务管理器分别位于不同的分布式系统的不同节点之上。简单的说，就是一次大的操作由不同的小操作组成，这些小的操作分布在不同的服务器上，且属于不同的应用，**分布式事务需要保证这些小操作要么全部成功，要么全部失败。本质上来说，分布式事务就是为了保证不同数据库的数据一致性**。或者，在换一句话说，分布式事务 = n 个本地事务。通过事务管理器，达到 n 个本地事务要么全部成功，要么全部失败。



## SEATA应运而生

那有什么方案解决上述的这些难点和痛点呢？

SEATA作为一款开源的分布式事务解决方案应运而生，其致力于在微服务架构下提供高性能和简单易用的分布式事务服务。

官方网址：https://seata.io/zh-cn/index.html

GitHub: https://github.com/seata/seata



### 愿景和诞生的鸟巢

- 微服务架构下，易用、高效的分布式事务解决方案。

- 技术积累

  - 内部产品：TXC、XTS
  - 商业化产品：GTS、DTS

- 愿景：像使用本地事务一样使用分布式事务，提供一站式的分布式事务解决方案



### 特性

1. **微服务框架支持**：目前已支持 Dubbo、Spring Cloud、Sofa-RPC、Motan 和 grpc 等RPC框架，其他框架持续集成中。
2. **高可用**: 支持基于数据库存储的集群模式，水平扩展能力强。
3. **高可扩展性**: 支持各类配置中心、注册中心、序列化、存储、协议序列化、负载均衡等SPI扩展。
4. **AT自动补偿模式**: 提供无侵入自动补偿的事务模式，目前已支持MySQL、Oracle的自动补偿模式、PostgreSQL、H2开发中。
5. **TCC模式**: 支持用户使用TCC灵活扩展事务。
6. **Saga模式**：提供长事务河服务编排解决方案。





## 【介绍篇】

- [微服务开发的最大痛点 - 分布式事务SEATA入门简介](https://mp.weixin.qq.com/s/JQn1AeQzAuLR259hm5659Q)



## 【实战篇】

- [微服务痛点 - 基于Dubbo + Seata的分布式事务(AT)模式](https://mp.weixin.qq.com/s/rIaW6psH9mNfHnM6lW-22Q)

 讲解视频: https://www.bilibili.com/video/BV1bt4y1k72o/

