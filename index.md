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


Docker可以将应用与依赖项打包成容器。解放困扰在系统配置上的开发人员，同时增强应用的便携性。

{% if site.edge == true %}
{% capture ce-edge-section %}

## Docker CE Edge

Docker社区前瞻版提供以月为周期进行发布，在使用新功能的同时还可以快速地验证bug的修复情况。前瞻版本的支持周期仅为一个月。一旦新的前瞻版本放出，不再对旧版进行更新。 

发布的稳定版不在前瞻版发布，因此 Linux用户需要同时订阅稳定版。

Docker社区版不受商业支持。

获取更多关于Docker版本订阅及预期支持, 访问[Docker channels](/engine/installation/#docker-channels).

<!-- This button toggles the div below, and hides itself when clicked -->
<a id="ce-edge-readmore-btn" onclick="$(this).hide(); ga('send', 'event', 'ce-edge-readmore', 'click', 'CE engagement');" data-target="#ce-edge-readmore" data-toggle="collapse" class="button outline-btn collapse in">Read more about Docker CE Edge releases</a>

<div markdown="1" id="ce-edge-readmore" class="collapse" data-target="#ce-edge-readmore-btn" data-toggle="collapse">

此页列举的特征仅在Docker社区前瞻版可用。
一旦新特性可用，API和CLI依赖文档就会覆盖下述特性。
但**Docker社区稳定版在收录特性前，完整文档陈列的部分功能可能不可用。**

### Docker社区前瞻版新特性

<ul class="nav nav-tabs">
  <li class="active"><a data-toggle="tab" data-target="#1704">17.04</a></li>
  <!--<li><a data-toggle="tab" data-target="#1705">17.05</a></li>-->
</ul>
<div markdown="1" class="tab-content">
<div markdown="1" id="1704" class="tab-pane fade in active">

#### Docker社区前瞻版 17.04

下述主要特征和改变将会包括在Docker社区前瞻版17.04中。
继续阅读或直接跳转至：[API and CLI](#api-and-cli),
[Daemon](#daemon), [Dockerfile](#dockerfile), [Services](#services), or
[Stacks](#stacks).

[阅读完整的发布记录](https://github.com/docker/docker/releases/tag/v17.04.0-ce){: target="_blank" class="_" }

##### API and CLI

- Add `--device-cgroup-rule` flag to give containers access to devices that appear
  after the container is started. {% include github-pr.md pr=22563 %}
  
- Allow swarm nodes to join with `--availability=drain` to prevent them from
  taking non-manager workloads. {% include github-pr.md pr=24993 %}

- Add `publish` and `expose` filters to `docker ps`, so that containers can be
  filtered by port or port range for TCP or UDP protocols {% include github-pr.md pr=27557 %}

- Add `--no-trunc` and `--format` flags to the `docker service ls` command, and
  as well as the ability to specify the default format for `docker service ls`
  using the `ServicesFormat` option to the Docker CLI. Also add a
  `docker stack services` command. {% include github-pr.md pr=28199 %}

- Add ability to filter plugins by whether they are enabled or disabled in
  `docker plugin ls` output. {% include github-pr.md pr=28627 %}

- Add `mode` option to `--log-opts` flag for both `docker` and `dockerd`. If set
  to `non-blocking`, and the log buffer fills up, log messages will be lost, but
  the container will not block. The `max-buffer-size` option controls the
  maximum size of the ring buffer. Defaults to `blocking`, which will cause the
  container to block if messages cannot be logged. See
  [Options for all drivers](/engine/admin/logging/overview.md#options-for-all-drivers).
  {% include github-pr.md pr=28762 %}

- It is no longer possible to inadvertently pull images on an architecture where
  they will not run. {% include github-pr.md pr=29001 %}

- It is now possible to create AWS log groups when using the AWS logging driver.
  See [`awslogs-create-group`](engine/admin/logging/awslogs.md#awslogs-create-group).
  {% include github-pr.md pr=29504 %}

- Add the ability to filter `docker network ls` output by creation time, using
  the `{% raw %}{{CreatedAt}}{% endraw %}` format specifier.
  {% include github-pr.md pr=29900 %}

- Named but untagged images are now removed if you run `docker image prune` if
  `--dangling-only` is set to `true`. {% include github-pr.md pr=30330 %}

- Add `--add-host` flag to `docker build`, which will add entries to the
  `/etc/hosts` file of a container created from that image. The `/etc/hosts`
  file is not saved within the image itself. {% include github-pr.md pr=30383 %}

- Prevent `docker network ls` from pulling all the endpoints, to reduce
  impact on the network. {% include github-pr.md pr=30673 %}

- Windows-specific commands and options no longer show in command help text on
  non-Windows clients. {% include github-pr.md pr=30780 %}

- When you specify an IP address when running `docker network connect`, the
  IP address is now checked for validity. {% include github-pr.md pr=30807 %}

- Add the ability to customize bind-mount consistency to be more appropriate
  for some platforms and workloads. Options are `consistent` (the default),
  `cached`, or `delegated`. {% include github-pr.md pr=31047 %}

##### Daemon

- Docker Daemon logging settings no longer affect the `docker build` command.
  {% include github-pr.md pr=29552 %}

- Add a `registry-mirrors` configuration option for the Docker daemon, which
  replaces the daemon's registry mirrors with a new set of registry mirrors.
  {% include github-pr.md pr=29650 %}

- Add the ability to specify the default shared memory size for the Docker
  daemon, using the `--default-shm-size` or the `default-shm-size` key in
  `daemon.json`. {% include github-pr.md pr=29692 %}

- Add a `no-new-privileges` configuration option for the Docker daemon, which
  prevents unprivileged containers from gaining new privileges.
  {% include github-pr.md pr=29984 %}

- If a Docker client communicates with an older daemon and attempts to perform
  an operation not supported by the daemon, an error is printed, which shows
  the API versions of both the client and daemon.
  {% include github-pr.md pr=30187 %}

- The Docker daemon no longer depends upon `sqlite`. This change means that it
  is not possible to upgrade the Docker daemon from version 1.9 directly to the
  latest version. It is recommended to upgrade from one major version to the
  next, in sequence. {% include github-pr.md pr=30208 %}

##### Dockerfile

- Using the pattern `**/` in a Dockerfile now (correctly) behaves the same as
  `**`. {% include github-pr.md pr=29043 %}

- Time values less than 1 second are no longer allowed in health-check options
  in the Dockerfile. {% include github-pr.md pr=31177 %}

##### Services

- When a service is updated with both `--secret-add` and `--secret-rm` in the
  same operation, the order of operations is now changed so that the
  `--secret-rm` always occurs first. {% include github-pr.md pr=29802 %}

- Add the ability to create or update a service to be read-only using the
  `--read-only` flag. {% include github-pr.md pr=30162 %}

- Docker now updates swarm nodes if the swarm configuration is updated.
  {% include github-pr.md pr=30259 %}

- Add topology-aware placement preferences for Swarm services. This feature
  allows services to be balanced over nodes based on a particular user-defined
  property, such as which datacenter or rack they are located in.
  See [Control service scale and placement](/engine/swarm/services.md#control-service-scale-and-placement).
  {% include github-pr.md pr=30725 %}

- Add the ability to customize the stop signal which will be sent to nodes, when
  creating or updating a service. {% include github-pr.md pr=30754 %}

- Add the ability to address a secret by name or prefix, as well as ID, when
  updating it. {% include github-pr.md pr=30856 %}

- Add the ability to roll back to a previous version of a service if an
  updated service fails to deploy. Several flags are available at service
  creation or update,to control the rollback action, failure threshold,
  monitoring delay, rollback delay, and parallelism.
  {% include github-pr.md pr=31108 %}

- Add the ability to specify the stream when using the Docker service logs API.
  {% include github-pr.md pr=31313 %}

- Add `--tail` and `--since` flags to `docker service logs` command, to filter
  the logs by time or to show the tail of the logs and show new content as it
  is logged. {% include github-pr.md pr=31500 %}

- Add a `--verbose` flag to the `docker inspect` command. For swarm networks,
  this flag shows all nodes and services attached to the network.
  {% include github-pr.md pr=31710 %}

##### Stacks

- Compose file version 3.2 is now supported. This includes support for different
  types of endpoints and expands the options you can use when specifying mounts.
  {% include github-pr.md pr=31795 %}

</div> <!-- 17.04 -->
<!--<div id="1705" class="tab-pane fade">TAB 2 CONTENT</div>-->
</div> <!-- tab-content -->
</div> <!-- ce-edge-readmore -->
{% endcapture %} <!-- from line 13 -->
{{ ce-edge-section | markdownify }}
{% endif %}

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

## 组件

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
    <!--organic row 2-->
    <!--editions-->
    <div class="col-sm-12 col-md-12 col-lg-4 block">
        <div class="component">
            <div class="component-icon">
                <a href="engine/installation/"> <img src="../images/apple_48.svg" alt="Docker Editions"> </a>
            </div>
            <h3 id="editions"><a href="engine/installation/">Docker的版本</a></h3>
            <p>展现Docker平台的表格及桌面、服务器、云服务提供商安装者的超集。</p>
        </div>
    </div>
    <!--compose-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="compose/overview/"> <img src="../images/compose_48.svg" alt="Docker Compose"> </a>
                </div>
                <h3 id="compose"><a href="compose/overview/">Docker Compose</a></h3>
                <p>使用多个容器、服务、集群配置定义应用程序栈。</p>
        </div>
    </div>
    <!--machine-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="machine/overview/"> <img src="../images/machine_48.svg" alt="Docker Trusted Registry"> </a>
                </div>
                <h3 id="machine"><a href="machine/overview/">Docker Machine</a></h3>
                <p>自动化供给网络或云中的容器。Windows、macOS及Linux均可使用。</p>
        </div>
    </div>
    <!--organic row 3-->
    <!--cloud-->
        <div class="col-sm-12 col-md-12 col-lg-4 block">
            <div class="component">
                <div class="component-icon">
                    <a href="docker-cloud/"> <img src="../images/cloud_48.svg" alt="Docker Cloud"> </a>
                </div>
                <h3 id="docker-cloud"><a href="docker-cloud/">Docker云</a></h3>
                <p>用来构建、测试、发布Docker镜像至主机的服务。</p>
            </div>
        </div>
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
    <!-- end real row-->
    </div>
<!-- end component-container 2-->
</div>
