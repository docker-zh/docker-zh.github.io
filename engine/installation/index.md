---
description: Lists the installation methods
keywords: docker, installation, install, docker ce, docker ee, docker editions, stable, edge
redirect_from:
- /installation/
- /engine/installation/linux/
- /engine/installation/linux/frugalware/
- /engine/installation/frugalware/
title: 安装Docker
---

## Docker版本

Docker有两个可用版本：

- **Docker企业版（Docker Enterprise Edition，简称Docker EE）**是为在生产环境中以弹性的方式构建、承载、运行商业级别的应用程序的企业开发及或IT团队设计的。Docker企业版受到行业内的集成、认证及支持，为企业提供业内最安全的容器平台以现代化的方式运行应用程序。获取包括支付方式在内的更多信息，访问：[Docker企业版](https://www.docker.com/enterprise-edition/){: target="_blank" class="_" }.

- **Docker社区版（Docker Community Edition，简称Docker CE）**适用于初次使用Docker并尝试基于容器构建应用的开发者或小型团队。Docker社区版在桌面、服务器及云端均可获得。Docker社区版为Windows和macOS提供了原生的实验环境帮助用户专注于学习Docker。用户可以通过单一的环境来构建并分享容器，使开发管线自动化。Docker社区版分为**stable稳定版**和**edge前瞻版**。

  - **稳定版stable**每季度发布一次并且提供四个月的支持。
  - **前瞻版edge**每个月发布一次并仅在当月提供技术支持。在Linux发行版订阅了前瞻版本的用户，也应该同时订阅稳定版。

  获取关于Docker社区版的更多信息，访问：[Docker社区版](https://www.docker.com/community-edition/){: target="_blank" class="_" }。

- **Docker云**是基于Docker，使用户可以通过不同的云服务提供商发布应用程序的平台。获取使用Docker云的更多信息，访问[Docker云](#docker-cloud)。

## 支持的平台

Docker社区版和企业版可以在Linux, 云, Windows还有macOS平台运行。使用下面的表格来选择适用自己的安装方式。链接会直接跳转至该**平台**的安装指南。

{% include docker_platform_matrix.md %}

访问[Docker云](#on-docker-cloud)获得Digital Ocean、Packet、SoftLink及自有设备的安装指南。

## 基于时间的发布日程

从Docker17.03起，Docker使用基于时间的发布日程，概述如下。

{% include docker_schedule_matrix.md %}

### 早期版本

在[Docker档案](/docsarchive/)获取安装早期Docker的版本的简介。

## Docker Cloud

还可以使用Docker云自动化 提供并管理您的云实例。

* [Amazon Web Services设置向导](/docker-cloud/infrastructure/link-aws.md)
* [DigitalOcean设置向导](/docker-cloud/infrastructure/link-do.md)
* [Microsoft Azure设置向导](/docker-cloud/infrastructure/link-azure.md)
* [Packet设置向导](/docker-cloud/infrastructure/link-packet.md)
* [SoftLayer设置向导](/docker-cloud/infrastructure/link-softlayer.md)
* [通过Docker云代理使用自有设备](/docker-cloud/infrastructure/byoh.md)

我们同样提供在AWS和Azure使用Docker的官方解决方案。你可以分别在[这里](/docker-for-aws/why/) 和 [这里](/docker-for-azure/why/)详细了解AWS的Docker和Azure的Docker的理由。

* [AWS的Docker](/docker-for-aws/)
* [Azure的Docker](/docker-for-azure/)

## 开始使用

安装好Docker后, 通过此链接[开始使用Docker](/engine/getstarted/)学习Docker的基础知识，然后在[应用教程](/engine/getstarted-voting-app/)学习如何发布成熟的应用程序。
