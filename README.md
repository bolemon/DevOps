
# 前言

> 最近工作收尾了，想着把这段时间开发的这个平台放出来，这个平台在新浪内部的一些部门中已经开始使用，觉得还不错，后续的一些功能还会不断的完善！下面是这个平台的一些简答介绍，有兴趣的大佬可以看看。




# 自动化运维平台

## 一、仪表盘介绍

自动化运维平台链接：[http://devops.linuxgc.com/](http://devops.linuxgc.com/)

![1574410036694](http://www.linuxgc.com/image/1574410036694.png)



#### 1. 作用：

**统计网站进行过的所有项目上的处理**



#### **2. 功能包括：**

​		**1）新增项目**

​		**2）处理工单**

​		**3）新增问答**

​		**4）分享同济**

​		**5）新增互动**

​		**6）新增页面**

​		**7）访问来源**

​		**8）每周工单处理数**



------



## 二、功能模块1-项目管理

![1574410805430](http://www.linuxgc.com/image/1574410805430.png)



#### 1. 作用：

**展示项目名称、项目描述、项目地址详细信息**

#### 2. 功能实现：

​		该页面直观的展示了所有存在的项目，便于管理与查看。



------



## 三、功能模块2-代码发布

***在代码发布模块中有以下三个标签：***



#### 1. 申请发布

**1）作用：填写发布项目具体内容，便于整理和提交审批**

**2）功能实现描述：**

![1574414507270](http://www.linuxgc.com/image/1574414507270.png)

​		在日常运维工作中，代码发布可能是最普遍的一项工作之一，尤其是网页代码的更新，碎片化发布需求非常频繁。在前期开发人员比较少时，还可以由自己 来上服务器通过脚本来发布代码。但随着公司项目的增多，更多的开发人员加入到公司，发布代码需求开始增多，这就占用了我大部分时间，经常的被打断其它工作 来发布代码，非常地不爽，然后开始想解决方法；

​		当然，发布代码肯定是运维的职责之一了，但频繁的发布导致运维大部分时间浪费在重复的操作上，非常的不值得。基于此，开始限制代码发布频率，要求把 不是很紧急的更新延后到一周中的几个时间点。但实施起来效果不理想，治标不治本，原因是你不能强制把需要立即上线的更改延后。实施这样的定时发布，有可能 影响项目的快速迭代；

​		想到这样子下去也不是办法，会造成工作很被动，于是开始着手建立以Web操作方式，结合jinkens，git，python来实现自动代码发布。最终实现以上图中的项目发布页面；



------



#### 2. 发布列表

**1）作用：审核发布项目是否通过并测试上线**

**2）功能描述：**

![1574414541154](http://www.linuxgc.com/image/1574414541154.png)

​		在申请项目发布以后，负责人可以进入发布列表查看预处理发布的项目，项目的详细信息都在页面展示，等待负责人的确认处理；

​		负责人点击“处理”按钮，这时进入上线流程界面：

​		① 审核：项目发布申请提出后，在列表中展示为申请状态；

![1574414611865](http://www.linuxgc.com/image/1574414611865.png)



​		点击处理，确认信息后下一步；

![1574414647974](http://www.linuxgc.com/image/1574414647974.png)



​		② 测试：项目审核通过后，状态修改为已审核；

![1574414715275](http://www.linuxgc.com/image/1574414715275.png)

​	

​		③ 灰度：项目测试通过后，状态变为灰度；

![1574414764375](http://www.linuxgc.com/image/1574414764375.png)



​		④ 上线：项目到灰度阶段后，再一次处理完成上线，上线后项目从项目列表移除；

​		⑤ 验证结果：登录服务器查看代码目录是否有代码上线。

![1574415182061](http://www.linuxgc.com/image/1574415182061.png)



------



#### 3. 发布历史

**1）作用：存放所有上线代码**

**2）功能描述：**

![1574415257751](http://www.linuxgc.com/image/1574415257751.png)



​		该模块记录所有上线成功或失败的所有结果，可通过点击“详情”查看代码上线的执行结果。

![1574415765955](http://www.linuxgc.com/image/1574415765955.png)



------



## 四、功能模块3-用户权限管理

***在用户权限管理模块中有以下两个标签：***



#### 1. 用户管理

**1）作用：管理用户信息**

**2）功能描述：**

![1574660779936](http://www.linuxgc.com/image/1574660779936.png)

​		

​		可以灵活、快捷且方便的去对用户进行增、删、改、查，还可以修改该用户所属组。

![1574660971202](http://www.linuxgc.com/image/1574660971202.png)



------



#### 2. 用户组管理

**1）作用：管理用户组信息**

**2）功能描述：**

![1574661078523](http://www.linuxgc.com/image/1574661078523.png)

​		

​		可以对用户组进行删（删除用户组）、改（修改用户组权限，给相应的用户组添加或删除权限）、查（查看用户组）。

![1574661969557](http://www.linuxgc.com/image/1574661969557.png)



------



## 五、功能模块4-工单系统

***在工单系统模块中有以下三个标签：***



#### 1. 申请工单

**1）作用：创建工单**

**2）功能描述：**

![1574662526213](http://www.linuxgc.com/image/1574662526213.png)

​		用户可以在工单系统创建工单，可以选择工单类型、编辑工单标题和工单内容，创建成功后可以跳转处理工单页面。

​		工单类型：方便对应的人员去处理相关工单；

​		工单标题：简单的说明问题；

​		工单内容：详细的对工单进行问题描述，以及如何出现，怎样出现的错误，方便人员进行复现及排错。



------



#### 2. 处理工单

**1）作用：可以对已申请的工单进行处理**

**2）功能描述：**

![1574662644737](http://www.linuxgc.com/image/1574662644737.png)



​		页面展示所有工单相关的信息，包括：工单标题，工单内容，工单状态，工单类型，申请人，申请时间，可以进行的操作；

​		管理员可以对已申请的工单进行一系列处理或驳回，管理员点击接受按钮，工单状态会变为处理中；

![1574662813748](http://www.linuxgc.com/image/1574662813748.png)



​		若管理员无法解决工单问题或接受错误工单，则可以点击取消，则工单状态又会变回申请，等待对应人员接受并处理工单；

​		若管理员发现工单已有相似问题正在解决或已解决，又或者无法复现是没有意义的问题，可以选择驳回处理，不进行处理，驳回后的工单会放入工单历史；

​		接受工单后，管理员再次点击处理可以对工单进行处理，提出处理意见后确认即可，处理确认后将已处理工单放入工单历史项目。

![1574662887193](http://www.linuxgc.com/image/1574662887193.png)



------



#### 3. 工单历史

**1）作用：查看历史工单的处理情况**

**2）功能描述：**

![1574663784794](http://www.linuxgc.com/image/1574663784794.png)

​		页面展示所有历史工单相关的信息，包括：工单标题，工单内容，工单状态，工单类型，申请人，处理意见，完成时间；

​		工单历史中记录之前所有的工单处理情况，已处理工单状态为完成，驳回工单的状态为取消，处理意见为处理过程或处理方式，完成时间可以明确该问题存在时间与实际解决时间。



------



## 六、功能模块5-任务下发

***在任务下发模块中有以下三个标签：***



#### 1. 添加ad-hoc任务

**1）作用：对主机组发送命令直接获取结果**

**2）作用描述：**

![1574664551603](http://www.linuxgc.com/image/1574664551603.png)



​		该模块集成了自动化工具ansible的各种功能，可以通过web界面对服务器进行一系列操作，并展示在web页面，可以直观的看到内容；

​		我们可以填写主机组，使用的模块，还有执行的动作、命令，最后在下面的展示框得到查询的结果，一目了然；

​		我们还可以查看历史记录，包括：执行的模块，执行的主机组，执行的动作，执行人是谁，执行时间，还有结果或取得详情；

![1574668494152](http://www.linuxgc.com/image/1574668494152.png)



​		我们可以点击详情，里面有我们最终获取到的结果，返回的内容全都可以展现出来

![1574668612440](http://www.linuxgc.com/image/1574668612440.png)



------



#### 2. 添加playbook任务

**1）作用：上传文件至服务器**

**2）功能描述：**

![1574668916852](http://www.linuxgc.com/image/1574668916852.png)

​		我们可以通过该模块上传文件到服务器上，添加任务后会跳转任务列表模块。



------



#### 3. 任务列表

**1）作用：执行任务下发添加的playbook任务**

**2）功能描述：**

![1574669372291](http://www.linuxgc.com/image/1574669372291.png)



​		我们可以在该页面看到之前提交的任务，包括：任务名称，playbook内容，执行状态，执行时间，还有可以进行的一些列操作；

​		我们可以点击执行，任务会变成已执行状态，并把文件上传到服务器上，并可以查看详情查看最终返回结果

![1574669533031](http://www.linuxgc.com/image/1574669533031.png)

![1574669548637](http://www.linuxgc.com/image/1574669548637.png)













# 第二部分——资产管理平台



## 一、首页介绍

CMDB管理平台链接：[http://cmdb.linuxgc.com/](http://cmdb.linuxgc.com/)

![1574671063152](http://www.linuxgc.com/image/1574671063152.png)



#### 1.作用：

**展示管理平台的数据及功能**



#### 2.功能描述：

​		**1）展示了管理平台的部分内容**

​		**2）统计了访问平台的数据量**

​		**3）统计了平台的销售额，订单量，新增用户等数据**

​		**4）将部分数据以图形化的形式展现出来**



------



## 二、功能模块1-数据表的管理

***在数据表的管理模块中有以下十个标签：***



#### 1. 业务线表

**1）作用：展示管理业务线**

**2）功能描述：我们可以通过该页面对业务线进行增删改查的管理操作；**

![1574671883803](http://www.linuxgc.com/image/1574671883803.png)

​		

​		点击编辑可以进入以下业务线信息的修改页面，还可以查看业务线的历史修改情况。

![1574671961323](http://www.linuxgc.com/image/1574671961323.png)



------



#### 2. 内存表

**1）作用：对我们的内存信息进行管理展示**

**2）功能描述：我们可以通过该页面对内存信息进行增删改查；**

![1574672259880](http://www.linuxgc.com/image/1574672259880.png)



​		点击编辑可以进入以下内存信息的修改页面，还可以查看内存信息的历史修改情况。

![1574672143840](http://www.linuxgc.com/image/1574672143840.png)



------



#### 3. 服务器表

**1）作用：对我们的服务器信息进行管理展示**

**2）功能展示：我们可以通过该页面对服务器信息进行增删改查；**

![1574672451846](http://www.linuxgc.com/image/1574672451846.png)



​		点击编辑可以进入以下服务器信息的修改页面，还可以查看服务器信息的历史修改情况。

![1574672681873](http://www.linuxgc.com/image/1574672681873.png)



![1574672689188](http://www.linuxgc.com/image/1574672689188.png)



------



#### 4. 机房表

**1）作用：对我们的机房信息进行管理展示**

**2）功能展示：我们可以通过该页面对机房信息进行增删改查；**

![1574672774119](http://www.linuxgc.com/image/1574672774119.png)



​		点击编辑可以进入以下机房信息的修改页面，还可以查看机房信息的历史修改情况。

![1574672799670](http://www.linuxgc.com/image/1574672799670.png)



------



#### 5.标签表

**1）作用：对我们的标签信息进行管理展示**

**2）功能展示：我们可以通过该页面对标签信息进行增删改查；**

![1574672853408](http://www.linuxgc.com/image/1574672853408.png)



​		点击编辑可以进入以下标签信息的修改页面，还可以查看标签信息的历史修改情况。

![1574672882136](http://www.linuxgc.com/image/1574672882136.png)



------



#### 6.用户组表

**1）作用：对我们的用户组信息进行管理展示**

**2）功能展示：我们可以通过该页面对用户组信息进行增删改查；**

![1574673167749](http://www.linuxgc.com/image/1574673167749.png)



​		点击编辑可以进入以下用户组信息的修改页面，还可以查看用户组信息的历史修改情况。

![1574673182276](http://www.linuxgc.com/image/1574673182276.png)



------



#### 7.硬盘表

**1）作用：对我们的硬盘信息进行管理展示**

**2）功能展示：我们可以通过该页面对硬盘信息进行增删改查；**

![1574675078222](http://www.linuxgc.com/image/1574675078222.png)



​		点击编辑可以进入以下硬盘信息的修改页面，还可以查看硬盘信息的历史修改情况。

![1574675098007](http://www.linuxgc.com/image/1574675098007.png)



------



#### 8.网卡表

**1）作用：对我们的网卡信息进行管理展示**

**2）功能展示：我们可以通过该页面对网卡信息进行增删改查，启动和停止；**

![1574675175434](http://www.linuxgc.com/image/1574675175434.png)



​		点击编辑可以进入以下网卡信息的修改页面，还可以查看网卡信息的历史修改情况。

![1574675186740](http://www.linuxgc.com/image/1574675186740.png)



------



#### 9.资产记录表

**1）作用：对我们的网卡资产记录进行管理展示**

**2）功能展示：我们可以通过该页面对资产记录进行增删改查；**

![1574675248513](http://www.linuxgc.com/image/1574675248513.png)



​		点击编辑可以进入以下资产记录的修改页面，还可以查看资产记录的历史修改情况。

![1574675279359](http://www.linuxgc.com/image/1574675279359.png)





------



#### 10.错误日志表

**1）作用：对我们的报错日志记录进行管理展示**

**2）功能展示：我们可以通过该页面对错误日志记录进行增删改查；**

![1574675452178](http://www.linuxgc.com/image/1574675452178.png)



​		点击编辑可以进入以下错误日志记录的修改页面。

![1574675412940](http://www.linuxgc.com/image/1574675412940.png)



------





## 三、功能模块2-管理模块

***在数据表的管理模块中有以下一个标签：***



#### 1.日志记录

**1）作用：对我们的日志记录进行管理展示**

**2）功能展示：我们可以通过该页面对日志记录进行增删改查；**

![1574675643068](http://www.linuxgc.com/image/1574675643068.png)



------



## 四、功能模块3-认证和授权

***在数据表的管理模块中有以下三个标签：***



#### 1.权限

1）作用：将所有的权限都列举出来

2）功能介绍：将所有可拥有的权限一一列举出来，并展示对应的内容，包括：权限ID（授予用户权限只需要选择权限ID即可，数据库里也只记录ID就可以查出该用户的权限），权限名称，内容类型，代码名称，可以进行的操作；

![1574676008878](http://www.linuxgc.com/image/1574676008878.png)



​		点击编辑可以进入以下页面，对权限进行修改

![1574676206761](http://www.linuxgc.com/image/1574676206761.png)



------



#### 2.用户

**1）作用：管理用户信息**

**2）功能描述：可以灵活、快捷且方便的去对用户进行增、删、改、查**

![1574676291701](http://www.linuxgc.com/image/1574676291701.png)



​		页面展示了用户的用户名，电子邮件地址，名字，姓氏，职员状态，可以进行的操作；

​		点击编辑可以进入以下界面对用户进行修改；

​				修改个人基本信息和职员状态；

![1574676370788](http://www.linuxgc.com/image/1574676370788.png)



​				修改用户的权限与所属组，还有日期；

![1574676396708](http://www.linuxgc.com/image/1574676396708.png)

![1574676402428](http://www.linuxgc.com/image/1574676402428.png)



------



#### 3.组

**1）作用：管理用户组信息**

**2）功能描述：可以对用户组进行增（添加用户组）、删（删除用户组）、改（修改用户组权限，给相应的用户组添加或删除权限）、查（查看用户组）**

![1574676586495](http://www.linuxgc.com/image/1574676586495.png)

​		

​		点击增加可以添加用户组并选择性授予用户组的权限，将用户添加至该组则可以使用该组授予的权限。

![1574676700009](http://www.linuxgc.com/image/1574676700009.png)












