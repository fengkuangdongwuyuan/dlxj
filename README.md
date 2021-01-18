# dlxj
(电力巡检平台系统介绍)

# 平台介绍
本平台分为PC和安卓App两端，pc端为平台管理端，分为用户、部门管理、设备信息管理、巡检任务管理、设备缺陷、消缺管理等主要功能；app端主要为巡检人员使用，对于使用人员，拥有巡检任务、采集设备信息、缺陷上报等功能，管理员也可登录app端，可进行巡检任务创建、查看缺陷统计、巡视到位统计等功能。
平台结合百度地图SDK用于记录各个设备位置信息，同时可实时记录巡检人员行进轨迹，当巡检人员开始巡检任务时，即开始记录巡检人员行进轨迹，管理员可在pc端中控大屏处根据不同任务查询该任务行进轨迹。
## 联系方式
![image]
(https://img-blog.csdnimg.cn/20210118094354703.png)
手机：18612878499（微信）      李逍
## 演示地址
如需演示地址，请添加微信沟通获取
## 技术选型
1、环境
Java SDK 8
Apache Maven 3.6+
支持 Docker、k8s 等
2、主框架
Spring Boot 2.2
Spring Framework 5.2
Apache Shiro 1.6
App：安卓原生
3、持久层
Apache MyBatis 3.5
Alibaba Druid 1.1
Hibernate Validation 6.0（服务端验证）
Sharding JDBC 4.0（读写分离、分库分表）
4、视图层
Spring MVC 5.2
Beetl 3.1（视图模板引擎、替换JSP）
CSS框架：
Bootstrap 3.3
AdminLTE 2.4
JS框架及组件：
jQuery 1.12
layer 3.1
zTree 3.5
jqGrid 4.7
jquery-validation
wdScrollTab
webuploader
ueditor
toastr
5、工具组件
Logback 1.2
Apache Commons
对象序列化：FST 2.57
JSON 序列化：Jackson 2.10
Office 工具：POI 4.1
分布式任务调度：Quartz 2.3
全文检索引擎：ElasticSearch、Lucene
百度地图SDK
6、存储
数据库：Mysql
缓存：Redis

## 主要功能

*
系统管理
用户管理
主要功能包括：用户的维护、查询、授权角色、授权数据权限
数据权限包括：拥有的权限和管理的权限；用户管理的数据权限被定义为管理的权限。管理的数据权限你需要在二级管理员里进行配置。
组织管理
指组织机构也是部门，采用多级组织管理维护，无限层级，支持全国应用。
权限管理
角色管理，角色维护，是系统功能权限设置的基础，相当于权限分组，所有用户对应到相应权限角色，便具有该权限角色所赋予的所有菜单权限和操作权限
授权功能菜单：给当前角色设置菜单和权限，依树状形式展示：当前用户的管理员身份下的所有菜单和权限，如果当前用户管理身份为二级管理员，则列出的是二级管理员菜单权重以下的菜单；如果当前用户管理员身份是系统管理，则列出的是系统管理员菜单权重以下的菜单；如果当前用户管理员身份是超级管理员，则列出的是超级管理员菜单权重下的菜单。此举是为了更好的提高授权安全，不能越级授权，权限互相牵制等。
系统管理
菜单管理，菜单管理主要用于配置系统菜单和操作权限。菜单即系统的功能菜单项，操作权限是属于菜单权限的子项，也就是具体的一个操作或按钮，例如：某一个菜单是“商品管理”，其对应的权限可能包括“增加”、“修改”、“删除”、“审核”、“发布”等一系列的权限。
字典管理，是用来维护数据类型的数据，如下拉框、单选按钮、复选框、树选择的数据，方便系统管理员维护。主要功能包括：字典分类管理、字典数据管理
行政区划也是区域管理，采用多级维护，主要包括：国家、省、市、县。
系统监控
访问日志，系统访问留痕的一个日志记录，可记录：接入日志、修改日志、查询日志、登录登出。
数据监控，监控数据源信息、SQL执行效能统计、高并发下分析最慢的SQl有助于优化系统、URI访问统计
2、巡检任务与设备
巡检与缺陷
创建巡检任务
拆分巡检任务
查看某任务设备缺陷详情、巡视率、巡视设备
消息管理
设备缺陷信息
统计
设备信息管理
3、其他
线路图导出CAD
查看指定线路图
查看巡检人员轨迹
特殊设备标识
缺陷设备标识
## 业务图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210118094608421.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70#pic_center)
## 平台截图
![首页中控概览](https://img-blog.csdnimg.cn/20210118094714465.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70#pic_center)
![实景线路图](https://img-blog.csdnimg.cn/20210118094740318.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![线路图](https://img-blog.csdnimg.cn/20210118094740233.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![设备缺陷信息](https://img-blog.csdnimg.cn/20210118094740216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![设备详情](https://img-blog.csdnimg.cn/20210118094740204.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![巡检任务](https://img-blog.csdnimg.cn/20210118094740206.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![设备详情](https://img-blog.csdnimg.cn/20210118094740176.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![缺陷基础信息](https://img-blog.csdnimg.cn/20210118094740180.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![统计信息](https://img-blog.csdnimg.cn/20210118094740170.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTUxNDg2,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021011809494553.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021011809494580.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021011809494551.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021011809494538.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210118094944990.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210118094944968.png)
## 购前须知
1.项目内容：源码 + 数据库脚本（如需相关文档联系客服）。如有二开需求，定制开发需求可以随时联系我们。
2.售后服务：相关文档可以提供，其他不包教不包指导不包解答 ,这个价格做不到再包教包解答的服务。
3.代码加密和封装jar说明：提供的是全部源码，如需license,需要自行获取授权（获取办法文档提供）。
4.并发量说明：代码层面，尽量做到优化, 支持多少用户和并发等，得看你服务器配置，是否集群，负载均衡, 数据库读写分离，宽带情况等综合因素
5.系统应用案例：此平台为定制开发项目外包，已目前没有发现不稳定。
6.代码更新/升级购买说明：免费提供一年的更新升级服务，开发者将不定时更新。
7.第三方相关插件说明：第三方相关插件会特别标注出来，需自行去申请第三方账号
8.系统bug说明：只能说目前没有发现的bug,不保证没有，不保证浏览器都兼容，若您个人认为ui 界面或者其它一些功能细节和您想象的不一样不满意，请再三思或与工作人员沟通！
9.软件运行环境支持：购买前可以先咨询清楚，确定合适再购买，不确定勿下单，下单就视为确定合适。不欢迎鸡蛋里挑骨头，挑刺，找茬的客户，平时大家都比较忙，没时间扯皮。
特别声明：此平台源码一经购买不能退款的，诚信合作共赢，望理解，谢谢合作！
