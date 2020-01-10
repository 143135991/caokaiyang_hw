#**SE419-project**

###Overview

本次实验主要内容为在k8s集群上部署TinyURL生成与处理服务,k8s集群为master-slave模式下的双节点结构，
在集群上运行TinyURL服务的Docker镜像以部署短连接服务功能

###Details

**k8s集群建立**

+ 本次project以单master-单slave模式进行k8s集群的搭建
+ 集群以AWS云端提供的主机为运行平台
+ Master节点进行UnSchedule污染，不负责处理运算
+ slave负责本次project的所有运算需求
+ 本集群主要采用工具为kubeadm与kubectl

**TinyURL服务**

+ TinyURL服务部分由mysql数据库与yourls短连接服务组成
+ Mysql负责存储TinyURL短连接与对应URL的匹配关系
+ Yourls是一款以PHP为基础的开源短连接系统，主要功能为短连接的生成
+ Yourls可以接收一个URL，并在数据库中查找，若存在对应短连接则将其返回，否则生成与该URL对应的短连接并存储在数据库中
