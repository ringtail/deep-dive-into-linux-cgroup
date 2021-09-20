---
description: >-
  Linux Cgroup是容器运行时（Docker、Containerd等）的基础，社区中介绍Linux
  Cgroup的文档多、浅而杂，难以匹配实际遇到的相关问题。对于使用、开发与运维Kubernetes的开发者而言，与Linux
  Cgroup相关的问题非常常见也相当宽泛，包含监控指标异常、内核死锁/夯机、Pod/Node
  OOM等等，本系列文章希望深入浅出地覆盖Cgroup的方方面面。
---

# Deep Dive Into Linux Cgroup

### 为什么要写这个系列

大家好，我是阿里云容器服务的莫源，负责容器服务的系统研发。作为国内比较早期的一批容器研发人员，见证了容器技术在国内的萌芽、发展与爆发，随着容器技术的成熟，上层的生态也正以指数倍的形式蓬勃发展。非常庆幸自己也能够参与其中，见证这个伟大的云原生时代的到来。但是，有的时候也会觉得有些失落，高速的发展意味着长尾与脱节，大量的生态组件无法跟进社区的版本演进，过时的文档与文章产生误导性的指引，而这其中，又以容器运行时相关的内容为甚。一来是因为容器运行时相关的技术和内核的版本有比较强的关系，不同的版本、参数产生的影响可能南辕北辙；二来Kubernetes的自愈机制让太多的问题埋藏在看似稳定和鲁棒的表象之下。在实际的工作中，80%以上的容器运行时相关的问题都可以从Linux Cgroup出发进行排查和诊断，本系列也希望从功能介绍、源码触达、常见问题等多个方面来给大家介绍Linux Cgroup的方方面面，并将认为比较常用和有效的配套工具进行引入，协助开发能够更快、更准确地定位容器运行时相关的问题。

### 系列目录

* Linux Cgroup概述篇
* Linux Cgroup核心概念篇
* Linux Cgroup子系统篇
* Linux Cgroup延伸篇
* Linux Cgroup源码篇
* Linux Cgroup工具篇
* Linux Cgroup常见问题篇

