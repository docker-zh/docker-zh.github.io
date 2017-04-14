---
description: Home page for Docker's documentation
keywords: Docker, documentation, manual, guide, reference, api, samples
landing: true
title: Docker Documentation
notoc: true
notags: true
---
{% assign page.title = site.name %}

## 文档黑客马拉松，2017年4月17日至22日

<a href="/hackathon/"><img src="docs-hackathon-2.png" alt="Docker Docs Hackathon, April 17-22nd, 2017" style="max-width: 100%"></a>

修正文档中的错误来换取点数, 通过点数来换取[the swag store](http://www.cafepress.com/dockerdocshackathon)中的奖品. 每10点可以在购物过程中抵用1美元。从DockerCon周活动期间：2017年4月17日至21日。

[黑客马拉松明细](/hackathon/){: class="button outline-btn" style="margin:20px"}[查看Github上值得修复的bug](https://github.com/docker/docker.github.io/milestone/9){: class="button outline-btn" style="margin:20px"} [访问奖励商店](http://www.cafepress.com/dockerdocshackathon){: class="button outline-btn" style="margin:20px"}

## Docker简介


<div class="row">
<div markdown="1" class="col-xs-12 col-sm-12 col-md-12 col-lg-6 block">
### 学习Docker基础

开始学习Docker的概念、工具和命令。样例中展示了如何构建、推送、拉取Docker镜像，并将它们作为容器运行。
这篇教程详细的介绍了如何发布应用程序。

[开始基础教程](/engine/getstarted/){: class="button outline-btn"}
</div>

<div markdown="1" class="col-xs-12 col-sm-12 col-md-12 col-lg-6 block">
### 在Swarm模式下定义并发布应用

学习在生产环境中将容器彼此关联，定义服务，配置应用程序栈进行弹性部署。使用Compose Version 3的新特性Highlights以及集群模式。

[学习启动一个Docker应用](/engine/getstarted-voting-app/){: class="button outline-btn"}
</div>
</div>

## Docker Editions

<div class="row">
    <div markdown="1" class="col-xs-12 col-sm-12 col-md-12 col-lg-6 block">

    ### Docker企业版

    Docker企业版（Docker Enterprise Edition，简称Docker EE）**是为在生产环境中以弹性的方式构建、承载、运行商业级别的应用程序的企业开发及或IT团队设计的。Docker企业版受到行业内的集成、认证及支持，为企业提供业内最安全的容器平台以现代化的方式运行应用程序，Docker企业版提供高级[扩展](#docker-ee-add-ons) 例如：UCP和DTR.

    [了解更过关于Docker企业版的信息](/engine/installation/#platform-support-matrix){: class="button outline-btn"}
    </div>

    <div markdown="1" class="col-xs-12 col-sm-12 col-md-12 col-lg-6 block">

    ### Docker社区版

    适用于初次使用Docker并尝试基于容器构建应用的开发者或小型团队。Docker社区版在桌面、服务器及云端均可获得。Docker社区版为Windows和macOS提供了原生的实验环境帮助用户专注于学习Docker。用户可以通过单一的环境来构建并分享容器，使开发管线自动化。前瞻版本包括最新的特性，稳定版本相对可靠。

    [了解更多关于Docker社区版的信息](/engine/installation/#platform-support-matrix){: class="button outline-btn"}
    </div>
</div><!-- end row -->


## Run Docker anywhere

<div class="component-container">
    <!--start row-->
    <div class="row">
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="docker-for-mac/"> <img src="../images/apple_48.svg" alt="Docker for Mac"> </a>
                </div>
                <h3 id="docker-for-mac"><a href="docker-for-mac/">Mac上的Docker</a></h3>
                <p>基于macOS沙箱安全模型的原生应用，提供Mac上所有Docker工具。</p>
            </div>
        </div>
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="docker-for-windows/"> <img src="../images/windows_48.svg" alt="Docker for Windows"> </a>
                </div>
                <h3 id="docker-for-windows"><a href="docker-for-windows/">Windows上的Docker</a></h3>
                <p>原生Windows应用程序，提供Windows电脑上所有Docker工具。</p>
            </div>
        </div>
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="engine/installation/linux/ubuntu/"> <img src="../images/linux_48.svg" alt="Docker for Linux"> </a>
                </div>
                <h3 id="docker-for-linux"><a href="engine/installation/linux/ubuntu/">Linux上的Docker</a></h3>
                <p>在已经安装Linux发行版的计算机上安装Docker。</p>
            </div>
        </div>
    </div>
</div>

<div class="component-container">
    <!--start row-->
    <div class="row">
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="docker-cloud/"> <img src="../images/cloud_48.svg" alt="Docker Cloud"> </a>
                </div>
                <h3 id="docker-cloud"><a href="docker-cloud/">Docker云</a></h3>
                <p>用来构建、测试、发布Docker镜像的托管服务。</p>
            </div>
        </div>
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="docker-cloud/"> <img src="../images/cloud_48.svg" alt="Docker for AWS"> </a>
                </div>
                <h3 id="docker-cloud-providers"><a href="/engine/installation/#platform-support-matrix">Docker for AWS</a></h3>
                <p>在AWS上部署Docker应用。</p>
            </div>
        </div>
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="docker-cloud/"> <img src="../images/cloud_48.svg" alt="Docker for Azure"> </a>
                </div>
                <h3 id="docker-cloud-providers"><a href="/engine/installation/#platform-support-matrix">Docker for Azure</a></h3>
                <p>在Azure上部署Docker应用。</p>
            </div>
        </div>
    </div>
</div>

## 组件

<h5>Docker企业版扩展</h5>

<div class="component-container">
    <!--start row-->
    <div class="row">
    <!--UCP-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="datacenter/ucp/2.1/guides/"> <img src="../images/UCP_48.svg" alt="Docker Universal Control Plane"> </a>
                </div>
                <h3 id="ucp"><a href="datacenter/ucp/2.1/guides/">Docker通用控制面板</a></h3>
                <p>通过Docker通用控制面板(Docker Universal Control Plane，简称UCP)像管理单个主机那样管理Docker集群。</p>
            </div>
        </div>
    <!--DTR-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="datacenter/dtr/2.2/guides/"> <img src="../images/dtr_48.svg" alt="Docker Trusted Registry"> </a>
                </div>
                <h3 id="dtr"><a href="datacenter/dtr/2.2/guides/">Docker信任的Registry</a></h3>
                <p>在防火墙下安装企业镜像存储解决方案(Docker Tusted Registry，简称：DTR)管理镜像及权限。</p>
	    </div>
        </div>
    </div>
    <!-- end real row-->
</div>

<h5>Docker Tools</h5>

<div class="component-container">
    <!--start row-->
    <div class="row">
    <!--compose-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="compose/overview/"> <img src="../images/compose_48.svg" alt="Docker Compose"> </a>
                </div>
                <h3 id="compose"><a href="compose/overview/">Docker Compose</a></h3>
                <p>使用多个容器、服务、swarm配置来定义应用栈。</p>
            </div>
        </div>
    <!--machine-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="machine/overview/"> <img src="../images/machine_48.svg" alt="Docker Trusted Registry"> </a>
                </div>
                <h3 id="machine"><a href="machine/overview/">Docker Machine</a></h3>
                <p>自动化网络或云中的容器供给。Windows、macOS及Linux均可使用</p>
        </div>
    </div>
</div>


<!-- end component-container 2-->
</div>
