# 专业实践 - 清歌电商平台
## 1. 项目介绍

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
