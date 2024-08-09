## 部门职责

**ICT产品与解决方案**-数据通信产品线-数据通信研发管理部-数据通信协议开发部-**OAM协议开发部**

**1、**负责**OAM协议（检测）**和OAM适配领域的业务交付与能力构建

**2、**负责本领域技术规划与开发，支撑构建持续领先的解决方案竞争力

**实现低开销网络测量和高精度异常检测，提供超低时延和超高可靠的IP联结，打造OAM领域绝对竞争力**

## 个人业务

**简略：完成华为自研的VRP平台的开发需求，写代码，提交代码，合代码，审查，交付。**

## 交付流程(重要)

技术评审TR（Technical Review）

**需求-功能-分配-交付-产品-发布**

![image.png](C:\Users\l50039653\Desktop\个人笔记\pic\cae0d02aac20036087db1730d08244e1_578x452.png@900-0-90-f.png)

项目经理在下发任务的时候，会给写好的TR1、TR2文档。然后我们要根据这两个文档来写TR3，TR3文档的粒度要细化到代码里面的结构体或者DIM表字段如何定义等等。写好之后拉上相关人员来检视评审，如果没问题，就可以按照这个着手写代码了。

### IR/SR/AR

**RR：Raw Requirement 原始需求**->

**IR：Initial Requirement 初始需求**->

**SR：System Requirement 系统需求**->

**AR：Allocated Requirement 分配需求**

### DIM/DOM/DAM

DIM （Data Information Model）数据信息模型

DOM（Data Operation Model）数据操作模型

DAM（Data Application Model）数据订阅模型

## 开发经验(重要)

- 往现有函数里面加代码，多半门禁会挂，不是行数超了，就是圈复杂度超了。 **考虑一下项目需要的函数是否为新功能，如果是，可以创建一个新文件。** **如果确实需要加在已有函数里的话，可以考虑提出来一些老代码，单独封个函数。** 一定要提前看门禁，不然快要交项目的时候再搞很容易乱中出错。
- 在写代码的时候如果**看到了老代码有可以优化的点，也可以在了解了功能之后尝试重构**。如果对老代码**进行了优化重构，可以重新提个MR合入**。最好不要放在项目的MR里面，原因是项目最后在show的时候要体现代码LLT覆盖率等，如果带入太多无关代码不太好。
- 一个项目不要想着等全部开发完了一股脑怼到子系统上去，可以迭代式合MR。比如资源侧的写完了就先合入一波。**因为有一种很麻烦的情况是代码合并冲突。这个情况就是在我们写代码的期间，别人的代码合进去了，造成冲突。**我们要是想合的话就需要解决冲突，这个有时候会出现奇怪的问题，解决起来很占用时间，主要是怕写好的代码乱掉甚至没了，心里很慌。**（开发时合代码与其它同事的代码发生冲突怎么处理，自查，重要！！！！）**
- ISSUE就是codehub上给代码提意见的一种东西。可以别人提，也可以自己提，这个在开发过程中要重视起来，没事自己检视，请人检视，多提ISSUE。
- 假如代码合入了，但是我们自己发现一些bug或者自己的代码会引起一些问题，这个时候先赶紧提个自提单。问题单可以理解为代码的质量问题，一般是别人提给我们的。但是如果我们自己发现自己提的话，别人就不会提了。

## 转测过程

转测就是转给测试去测我们的代码，**转测前要自测和准备交付件**。

代码写完可以先找组里的同事帮忙检视一下，看看代码。要自己测一下功能，考虑一下各种场景，然后截图。

**DFX(design for X):**

表示面向产品非功能性属性的设计。这个其实就是连接网站然后跑很多测试，保证代码的质量。这个在整个开发流程中要占用比较长的时间，因为可能会遇到很多问题，可能是代码的问题、也可能是工具、用例的问题。

**代码白盒检查:**

一写完代码，就**应该设计LLT用例**，甚至**现在的敏捷开发还提倡在写代码之前就先设计好LLT用例**。这个是很重要的，包括覆盖率都是要在转测的时候提供的。

**文档编写:**

主要有 

**OMSYS**：OMSYS项目是OM交付件的统一管理平台。将OM交付件的写作、评审、归档、版本管理等集中管理，通过文件同源，保证各版本之间的数据的一致性 

**差异文档：**在历次升级过程中，多次出现由于特性差异导致的网上问题，所以后面在版本交付时同步提交与升级版本的特性差异文档

**规格网站：**就是记录产品和功能规格的，资料手册。

**翻译：**所有要对客户呈现的文字，都需要找翻译检视，比如说回显信息、错误信息等等。

**资料手册：**这个就是产品文档，给用户看的，里面会有功能、特性、如何配置的介绍。

# 发散性工作内容

## SVRP搭建

### 实验目的

SVRP相关实验是在搭建的虚拟环境下使用虚拟设备，通过对各类虚拟设备进行ip，协议等的配置，连接网络拓扑，最终构建一个完整的虚拟网络环境的过程。

### 实验过程

1、搭建本地虚拟机SVRP环境（网络接黄，申请虚拟机权限）

2、安装**VRP虚拟包环境**mount /dev/sda3 /opt

3、从**X-du平台**下载**cc大包**，在虚拟机内进行操作

4、拿到cc大包后，上传到/opt文件夹里，然后开始走流程：

- 首先解压cc大包，执行命令: tar -zxvf *****.cc
- 执行脚本：./v8install.sh
- 可以发现opt目录下多了两个文件夹‘svrp’和‘vrpv8’，进入‘svrp’文件夹
- **执行脚本./start_svrp.sh router1**新建一台虚拟路由器
- 最后如果没有报错，输入命令：**./time_client_start 1**
- 成功进入VRP环境

### 实验细节

**相关链接：**

**[SVRP环境速配版 - 【OAM协议开发部】讨论社区 - 3MS知识管理社区 (huawei.com)](https://3ms.huawei.com/km/groups/3850225/blogs/details/12391357?l=zh-cn)**

**[一键起SVRP - 【OAM协议开发部】讨论社区 - 3MS知识管理社区 (huawei.com)](https://3ms.huawei.com/km/groups/3850225/blogs/details/11909903)**

## SVRP中起两台路由器

1、进入SVRP虚拟环境（虚拟机）

2、执行**./time_client_start 1	./time_client_start2**命令起两台路由器，并进入华为VRP管理系统

3、建立连接过程

- 1.输入**system_view**命令进入系统视图
- 2.输入**sysname Router**命令来命名路由器加以区分
- 3.输入命令**interface GigabitEthernet 0/0/0**进入千兆接口GE0/0/0**（一般不用0/0/0因为是它是管理口）**
- 4.输入命令ip address 10.1.12.1 24配置IP地址
- **5.输入命令`display lldp neighbor brief`来查看该路由器端口直连的其它路由器的端口**
- 6.输入命令**disp interface brief**查看该路由器接口信息

## Git拉取代码与提交

1、在X-Du平台上找到关于VRP代码的git链接

2、**在WeCode Online上创建自己的个人实例**

3、新建空白文件夹，在文件夹中进行相关的操作

4、拉取终端，输入以下命令来初始化环境

~~~git
git mm init -u ssh://git@kwe-y.codehub.huawei.com:2222/DCP_DCPPlatform_VRPV8/manifest_vrpv8.git -b br_VRP_V8R24C00_sys_OAM -m vrpv8.xml -g all
~~~

5、使用vscode关于wecode的插件来**选择代码仓库中需要的代码进行下载**

6、改动代码，开始进行提交操作：

- 1.使用命令`git mm info`来查询当前本地代码的信息

- 2.本地代码没有分支，需要创建分支，代码为`git mm start vrp_bfd_lsl --all`用来创建个人分支

- 3.重新查询代码的信息，显示已经出现了个人的分支

- 4.使用命令`git st`来查询当前的代码状态

- 5.输入指令`git add .`首先在本地完成保存

- 6.使用vscode关于wecode的插件来完成commit，主要commit必须要填写相关的信息

- ~~~
  【问题单号or需求单号 Defect No.】
  【合入描述 Description】
  【架构相关头文件、关键资源变更是否通过架构CCB】NA
  ~~~

- 7.最后输入git mm upload指令完成提交，并获取MR的链接(**Merge_Requests)**

# BFD相关工作

## BFD内容学习整理

### 协议简介

对**相邻转发引擎**之间的通道提供轻负荷、快速故障检测。

提供一个**单一的机制**，能够用来**对任何媒介、任何协议层**进行实时地检测。

### 会话建立方式

BFD使用本地标识符（Local Discriminator）和远端标识符（Remote Discriminator）**区分同一对系统之间的多个BFD会话**。按照本地标识符和远端标识符创建方式的差异区分：

- 手工指定标识符的静态BFD会话
- 标识符自协商的静态BFD会话
- 协议触发的动态BFD会话：无需指定本地标识符和远端标识符。

### 检测方式

**异步检测模式**。各系统间按照协商好的**周期发送BFD控制报文**，如果某个系统**在检测时间内没有收到对端发来的报文，则将BFD会话的状态置为Down**。

### 特性

- 动态改变BFD参数，例如最小发送间隔、最小接收间隔、检测模式等，不影响会话的当前状态。
- 支持BFD会话绑定到VPN实例，实现BFD控制报文在指定VPN发送。

### 主要操作和命令

- **bfd** session-name **bind peer-ip** peer-ip //创建BFD for IPv4会话的绑定信息。

#### 全局命令

**使能全局bfd：**进入系统视图输入bfd命令，执行**commit**（只要进行了bfd的相关操作都记得要commit提交）命令提交配置

#### 标识符类

- 执行命令**discriminator** **local** *discr-value*，配置BFD会话的**本地标识符**。
- 执行命令**discriminator** **remote** *discr-value*，配置BFD会话的**远端标识符**。

**TIP：BFD会话两端设备的本地标识符和远端标识符需要分别对应，即，本端的本地标识符与对端的远端标识符相同，否则会话无法正确建立。**

#### 时间类

- 执行命令**min-tx-interval** *tx-interval*，配置发送间隔。
- 执行命令**min-rx-interval** *rx-interval*，配置接收间隔。
- 执行命令**detect-multiplier** *multiplier*，配置本地检测倍数。

**TIP：一旦检测到BFD会话Down，系统自动将本端的发送间隔和接收间隔调整为大于1000毫秒的一个随机值，当BFD会话的状态重新变为Up后，再恢复成用户配置的间隔时间。**

- 执行命令**wtr** *wtr-value*，配置分钟级BFD会话的等待恢复时间。

**TIP：**配置BFD会话的等待恢复时间WTR（Wait To Restore）。当BFD会话从状态Down变为状态Up时，BFD等待WTR超时后才将这个变化通知给上层应用。如果使用WTR，**用户需要手工在两端配置相同的WTR**。否则，当一端会话状态变化时，两端应用程序感知到的BFD会话状态将不一致。

#### 描述类

- 执行命令**description** *description*，配置BFD会话的描述信息。
- 可以执行**undo description**命令来删除BFD会话的描述信息。

#### 优先级类

#### 配置检查类

**TIP：只有配置完BFD会话参数并成功建立会话后，才能查看到BFD会话统计信息和BFD会话信息。**

- 使用**display bfd session** { **all** | **discriminator** *discr-value* | **dynamic** | **peer-ip** *peer-ip* [ **vpn-instance** *vpn-name* ] | **static** } [ **verbose** ]命令查看BFD会话信息。
- 使用**display bfd statistics**命令查看BFD全局统计信息。
- 使用**display bfd statistics session** { **all** | **static** | **dynamic** | **discriminator** *discr-value* | **peer-ip** *peer-ip* [ **vpn-instance** *vpn-name* ] }命令查看BFD会话统计信息。
- 使用**display bfd interface**命令查看使能BFD的接口信息。

## 配置BFD会话——单跳检测

### 实验目的

通过在单跳路径的两端建立BFD会话，实现BFD会话快速检测网络中的链路。

### 数据准备

根据**`display lldp neighbor brief`**命令发现Router1的Ethernet3/0/0口和Router2的Ethernet3/0/0口是直连的，所以要在这两个口上配置IP地址。

~~~
[~Router1-Ethernet3/0/0]ip address 10.1.1.1 24
[~Router2-Ethernet3/0/0]ip address 10.1.1.2 24
~~~

### 实验步骤

1、如数据准备所示配置两个路由器的接口的IP地址

2、配置两个接口之间的单跳路径检测

~~~
[~DeviceA] bfd
[*DeviceA-bfd] quit
[*DeviceA] bfd atoc bind peer-ip 10.2.1.2
[*DeviceA-bfd-session-atoc] discriminator local 10 //本端标识符10
[*DeviceA-bfd-session-atoc] discriminator remote 20 //对端标识符20
[*DeviceA-bfd-session-atoc] commit
[~DeviceA-bfd-session-atoc] quit

[*DeviceC] bfd ctoa bind peer-ip 10.1.1.1
[*DeviceC-bfd-session-ctoa] discriminator local 20 //本端标识符20
[*DeviceC-bfd-session-ctoa] discriminator remote 10 //对端标识符10
~~~

3、验证配置结果

配置完成后，在DeviceA和DeviceC上执行**`display bfd session all verbose`**命令，可以看到建立了一个多跳（Multi Hop）的BFD会话，且状态为Up。

4、对Router1接口执行**shutdown**操作，模拟链路故障。

5、再次执行**`display bfd session all verbose`**命令，可以看到BFD会话的状态为Down。

## BFD-MiniTask

**见BFD文件包**

# 开发工具

## Hyber -V

## git-mm git

## MobaXterm

功能强大的远程计算全能型终端神奇

## WeCode-Online

开箱即用的集成开发环境，用来建立一个IDE实例在里面进行编程

# 平台

## X-Du

X-Du项目管理平台是服务于数据通信产品线各版本经理、领域PM、SE、开发、测试等人员，支撑管理版本需求交付、项目迭代上车、问题单多维度度量、主干快速集成交付等业务，提升版本管理效率，使能项目管理数字化

## VRP

VRP是华为的通用路由平台，**是用来管理华为的数据通信产品包括路由器，交换机这些的通用操作系统。可以提供IP路由服务。**通过各种视图，命令行指令来进行交互。**但是随着以前cpu是单核的都在往多核发展，为了能够满足多核硬件处理能力**，在VRP5基础上开发了VRP8平台。不过现在相对较为稳定的还是VRP5平台，一个分布式的网络操作系统。VRP8通过多进程，组件化来满足未来需求。

竞品：思科-IOS，Juniper-JUNOS

### 命令集

```linux
interface GigabitEthernet 1/0/0	进入接口
```

```
shutdown	用来关闭当前接口
undo shutdown	用来开启当前接口
```

### 资源侧命令操作

[常见问题定位手段汇总 - 南京整机团队 - 3ms知识管理社区 (huawei.com)](https://3ms.huawei.com/hi/group/3947444/wiki_6373404.html)

# 技能知识学习

## Linux学习

**学习链接：[linux教程 - 3MS文档库 (huawei.com)](https://3ms.huawei.com/documents/docinfo/775415333478039552)**

**在 Linux 世界里，一切皆文件**

Linux **是一款操作系统**，**免费，开源**， 安全，高效，稳定， **处理高并发非常强悍**，现在很多的企业级的项目都部署到 Linux/unix 服务器运行。

### 基础

linux 的目录中**有且只要一个根目录 /**

为什么需要远程登录 Linux：服务器和项目是小组共享的。远程登录客户端有**Xshell5， Xftp5**

### vi与vim篇

vi 文本编辑器。

Vim 具有程序编辑的能力，可以看做是 Vi 的增强版本。

### 用户篇

`reboot`重启系统

登录一般不用root登录，因为它权限最大，防止操作失误。

登录后**再用`su - root`命令**来切换成系统管理员身份。

### 文件篇

- pwd：显示当前工作目录的绝对路径

- ls   [选项]	[目录或是文件]：查看当前目录的所有内容信息

- mkdir	[选项]	要创建的目录：创建一个目录

- rmdir	[选项]	要删除的空目录：**删除空目录**

- touch 文件名称：创建一个空文件

- cp [选项] source dest：拷贝文件到指定目录

  ​		-r ：递归复制整个文件夹

- rm	[选项]	要删除的文件或目录：删除文件或目录

  ​        -r ：递归删除整个文件夹

- mv /temp/movefile /targetFolder：移动文件

- cat	[选项] 要查看的文件：**只读方式查看文件**

- **\> 输出重定向 :  会将原来的文件的内容覆盖** 

- **>> 追加： 不会覆盖原来文件的内容，而是追加到文件的尾部。**

- **echo	[选项]	[输出内容]：输出内容到控制台**

### Shell编程（重要）

对于 JavaEE 和 Python 程序员来说，工作的需要，你的老大会要求你**编写一些 Shell 脚本进行程序或者是服务器的维护**，比如编写一个定时备份数据库的脚本。

Shell 是一个命令行解释器，它为用户提供了一个向 Linux 内核发送请求以便运行程序的界面系统级程序，用户可以用 Shell 来启动、挂起、停止甚至是编写一些程序。

### 开发平台Ubuntu

Ubuntu是一个以桌面应用为主的开源 GNU/Linux 操作系统，，支持 x86、amd64（即 x64）和 ppc 架构，由全球化的专业开发团队打造的。

## Git学习

本地版本控制系统->集中化版本控制系统->**分布式版本控制系统**

客户端并不只提取最新版本的文件快照，而是把代码仓库完整地镜像下来。 这么一来，任何一处协同工作用的服务器发生故障，事后都可以用任何一个镜像出来的本地仓库恢复。

更进一步，许多这类系统都可以指定和若干不同的远端代码仓库进行交互。藉此，你就可以在同一个项目中，分别和不同工作小组的人相互协作。

**直接记录快照，而非差异比较（与其他系统本质区别）**

**近乎所有操作都是本地执行**

**Git 保证完整性**

### Git三种状态

**已提交(committed)、已修改(modified)和已暂存(staged)。** 

已提交表示数据已经安全的保存在本地数据库中。 

已修改表示修改了文件，但还没保存到数据库中。 

已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。

![img](http://www.yiibai.com/uploads/images/201707/0607/744160702_48164.png)

由此引入 Git 项目的三个工作区域的概念：**Git 仓库、工作目录以及暂存区域**。

**基本的 Git 工作流程如下：**

1. 在**工作目录中修改文件**。
2. **暂存文件**，将文件的快照放入暂存区域。
3. 提交更新，找到暂存区域的文件，**将快照永久性存储**到 Git 仓库目录。

### 获取Git仓库

当你执行 `git clone` 命令的时候，默认配置下远程 Git 仓库中的每一个文件的每一个版本都将被拉取下来。

这会在当前目录下创建一个名为 “`git-start.git`” 的目录，并在这个目录下初始化一个 `.git` 文件夹，从远程仓库拉取下所有数据放入 `.git` 文件夹，然后从中读取最新版本的文件的拷贝。

### 更新提交仓库

#### 提交暂存

现在我们手上有了一个真实项目的 Git 仓库，在完成了一个阶段的目标之后，提交本次更新到仓库。

工作目录下的每一个文件都不外乎这两种状态：**已跟踪或未跟踪**。

~~~
git status 查看文件处于什么状态

使用命令 git add 开始跟踪一个新文件
~~~

#### 忽略文件

一般我们总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。

我们可以**创建一个名为 `.gitignore` 的文件**，列出要忽略的文件模式

#### 提交更新

$ git commit

另外，也可以在 `commit` 命令后添加 `-m` 选项，将提交信息与命令放在同一行

~~~
$ git commit -m "this is my commit info note."
[master 463dc4f] Story 182: Fix benchmarks for speed
 2 files changed, 2 insertions(+)
 create mode 100644 README.md
~~~

现在已经创建了第一个提交！ 可以看到，提交后它会告诉你，当前是在哪个分支(`master`)提交的，本次提交的完整 SHA-1 校验和是什么(`463dc4f`)，以及在本次提交中，有多少文件修订过，多少行添加和删改过。

Git 提供了一个跳过使用暂存区域的方式， 只要在提交的时候，给 `git commit` 加上 `-a` 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 `git add` 步骤

### 拉取远程仓库

我在之前的章节中已经提到并展示了如何添加远程仓库的示例，

运行 `git remote add <shortname> <url>` 添加一个新的远程 Git 仓库。

**从远程仓库中获得数据**，可以执行：**$ git fetch [remote-name]**

如果**使用 `clone` 命令**克隆了一个仓库，**命令会自动将其添加为远程仓库并默认以 “`origin`” 为简写**。 

### 推送远程仓库

当想分享你的项目时，必须将其推送到上游。 这个命令很简单：`git push [remote-name] [branch-name]`。

**$ git push origin master**

只有当你有所克隆服务器的写入权限，并且之前没有人推送过时，这条命令才能生效。 当你和其他人在同一时间克隆，他们先推送到上游然后你再推送到上游，你的推送就会毫无疑问地被拒绝。 你必须先将他们的工作拉取下来并将其合并进你的工作后才能推送。

## Git mm学习

### 操作模式

**工作目录（working directory）**：用于存放产品开发数据本地工作目录。

**索引（Index/stage）**：用于存放待提交数据的缓存区。

**本地库**：远端库的一个完整的拷贝，包括所有文件的修改记录，分支等。

**远端库/版本库**：本地库clone来源。

**HEAD**: 指向当前分支的指针。

<img src="C:\Users\l50039653\Desktop\个人笔记\pic\bc30b2617777db136789_639x286.png@900-0-90-f.png" alt="img" style="zoom: 150%;" />

### 基本操作

#### 下载类

创建代码仓库

- **git mm init** -u ${维护xml文件的仓库地址} -b ${xml文件所在分支} -m ${xml文件名} -g ${子仓归属的组名}

下载/更新代码

- **git mm sync**  （加上仓名可指定需要下载/更新的一个或多个仓）

创建本地分支

- **git mm start [branch_name] --all**

删除本地分支

- **git mm abandon [branch_name] --all**

#### 修改类

**git add .**	将当前目录修改文件**保存到缓存区**

**git commit**	提交修改到**本地库**

**git mm upload**	上传修改到**远端库**

#### 撤销类

**撤销未保存到缓存区**

- **git checkout -- filename/.** ：撤销指定文件/全部文件的修改
- **注意：参数中--很重要，不加的话就成了切换到另一个分支。**

**撤销已保存到缓存区**

- **git reset HEAD filename/.** ：撤销指定文件/所有文件的修改

**撤销已提交到本地库**

- **git reset --hard HEAD^**  ：回退到上一次commit的状态

**撤销已上传到远端库**

- 文件修改后，执行**git commit**到本地库，并**git mm upload**到远端库，可以使用**git revert commitid**

#### 查询类

**git mm info**	查询子仓信息

**git mm status**	遍历所有仓查看文件状态 

### YANG学习

