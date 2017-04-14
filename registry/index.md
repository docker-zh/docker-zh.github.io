---
description: High-level overview of the Registry
keywords: registry, on-prem, images, tags, repository, distribution
redirect_from:
- /registry/overview/
title: Docker Registry
---

## Docker Registry是什么？

Registry是无状态、高弹性的服务端应用， 用来储存或发布Docker镜像。Registry以[Apache license](http://en.wikipedia.org/wiki/Apache_License)协议开源.

## 为什么使用Docker Registry

You should use the Registry if you want to:

 * 控制镜像储存的位置
 * 拥有自己的镜像发布管线
 * 在本地工作流中，使镜像储存与发布紧密的结合在一起。
 
## 其他方案

[Docker Hub](https://hub.docker.com)提供免费、托管的仓库来实现零维护随时可用的效果以及其他附加特性（如：组织账号、自动化编译等等）。

需要商业支持的Registry版本不妨尝试：[Docker Trusted Registry](/datacenter/dtr/2.1/guides/index.md).

## 必要条件

Registry可以与**version 1.6.0 及以上版本的Docker引擎**协同工作。 
如果必须使用旧版的Docker，可以尝试[old python registry](https://github.com/docker/docker-registry).

## Registry基础操作

启动Registry

    docker run -d -p 5000:5000 --name registry registry:2

从Docker Hub拉取或构造镜像

    docker pull ubuntu

给镜像打标签使其指向私有Registry

    docker tag ubuntu localhost:5000/myfirstimage

推送镜像

    docker push localhost:5000/myfirstimage

拉取镜像

    docker pull localhost:5000/myfirstimage

停止Registry并移除所有数据

    docker stop registry && docker rm -v registry

## 接下来

阅读[Registry的详细介绍](introduction.md)，或跳转至[部署教程](deploying.md).
