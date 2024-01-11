# 专业实践 - 清歌电商平台
## 1. 项目介绍

**清歌电商平台**是一个基于**Spring Boot、Vue、Redis、MySQL、Mybatis**等技术的全栈应用程序。

平台可分为**用户端**和**管理员端**。

**用户端**功能如下：
+ **买卖商品**：用户可以浏览本电商平台的商品，选择购买感兴趣的商品，购买过程中提供了简单的结算和支付功能，且可以自行上架待出售的商品。
+ **购物车**：用户可以将多个商品添加到购物车，方便一次性结算多个商品。
+ **查看订单**：用户可以查看已下单的订单列表，包括订单号、商品信息、价格、数量等详细信息，并跟踪订单的配送状态。
+ **搜索**：用户可以通过关键字搜索电商平台上的商品，将符合条件的商品以及信息呈现给用户。
+ **推荐商品**：平台可以基于用户的浏览历史、购买历史和兴趣偏好等信息，为用户提供个性化的商品推荐。

**管理员端**功能如下：
+ **用户管理**：管理员可以查看注册用户列表，包括用户信息、购买历史等，可以对用户进行管理操作，例如禁用用户、重置用户密码等。
+ **商品管理**：管理员可以对上架的商品进行添加或下架，编辑现有商品的具体信息。

**技术实现**：

+ 后端使用**Spring Boot**框架实现
+ 数据库使用关系型数据库**MySQL**
+ 使用**Redis**缓存数据，提高系统的性能和响应速度
+ 使用**Mybatis**建立程序和数据库之间的连接，实现数据库的查询和修改
+ 前端使用**Vue**、**Java Script**开发用户界面，通过axios库与后端进行数据交互

## 2. 项目特色

## 3. 项目配置

本项目是基于Springboot + vue前后端分离的Web项目，开发工具为IDEA 2022.3，各软件版本如下：

- 数据库版本（MySQL）：
  
  mysql Ver 8.0.35 for Win64 on x86_64 (MySQL Community Server - GPL)，数据库相关下载和配置可自行参考百度，只要是8.0版本即可。

  Navicat 15 for MySQL，可视化访问MySQL软件，相关下载和配置可自行参考百度，版本15或16皆可。

- Redis（Windows系统）：

  前往github链接 [Redis下载与安装](https://github.com/tporadowski/redis/releases)
  下载 Redis-x64-5.0.14.1.zip（或最新版本即可），下载到本地解压缩即可。

- node.js + npm + vue.js 

  参考csdn链接 [node.js + npm + vue.js安装与环境配置](https://blog.csdn.net/jike11231/article/details/107834744/?ops_request_misc=&request_id=&biz_id=102&utm_term=%E5%AE%89%E8%A3%85npm&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-3-107834744.142) 按照步骤下载并安装最新版node.js和npm即可。

- 项目运行环境

  - 要求 IDEA 事先配置好 Maven，本项目采用 Maven 架构以实现不同开发平台快速搭建项目所需配置，Java VCM 环境为 JDK 8 版本（java version 1.8.0_191），高版本不适用，项目内置了 java 8 ，因此只需要 IDEA 的 Maven 配置正确，该项无需手动配置。IDEA 中项目运行/调试配置应当如下：
  ![](https://github.com/WoGiaoA/MajorPractice/blob/photos/1704959150894.jpg?raw=true)

- 项目运行详细过程

  配置好以上项目所需各种环境后，按照下述顺序依次启动前后端项目：

  * 新建数据库qingge，导入 */qingge-springboot/qingge.sql 以建表，修改application.yml文件为自己本地的数据库配置（包括账号密码等），其余无需修改。

  * 以管理员身份打开cmd窗口，进入到项目目录下*\qingge-vue\vue，首次运行项目需要依次输入npm install、npm run serve、npm run build（该指令需要在运行npm run serve返回正确结果后另开启一个cmd窗口运行），后续运行只需要在该目录下运行npm run serve即可，运行正确结果如下图：
  
  ![](https://github.com/WoGiaoA/MajorPractice/blob/photos/1704960079677.jpg?raw=true)
  ![](https://github.com/WoGiaoA/MajorPractice/blob/photos/1704960253281.jpg?raw=true)
  ![](https://github.com/WoGiaoA/MajorPractice/blob/photos/1704960670606.jpg?raw=true)

    执行完npm run build，出现 DONE Build complete. The dist directory is ready to be deployed. 说明前端成功运行。

  * 进入到 Redis 安装目录下，双击运行 redis-server.exe，如下图：
  ![](https://github.com/WoGiaoA/MajorPractice/blob/photos/1704960881321.jpg?raw=true)

  * 运行 IDEA 项目，启动 Springboot。

  * 在浏览器中输入 localhost:8080/login 以登录。
  

## 4. 成果展示
