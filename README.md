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

- Vue框架进行前端开发：

  使用vue框架进行前端开发，构建用户界面，将前端工程组件化，提高开发效率。Vue作为一款轻量级前端框架，大小只有18–21KB，工程搭建简单，仅需几行命令符。

  通过虚拟DOM和响应式避免了不必要的全局重新渲染，提升用户体验，使交互更加流畅。由于Vue框架的流行性，目前有许多基于Vue的npm扩展包和开发工具（如Vuex）。Vue可以在一个文件下统一管理所有外部插件的全局使用。并且，其突出优势在于可以**对数据进行双向绑定**，第三方组件库丰富，使用方便，提高开发效率。

![https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%871.png?raw=true](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%871.png?raw=true)

- 使用Maven对开发平台进行项目构建和依赖管理：

  其优点包括：

  - 原来的项目中需要的jar包必须手动“复制”、”粘贴” 到WEB-INF/lib 项目下，而借助Maven，可以将jar包仅保存在“仓库”中，有需要使用的工程只需要“引用”这个文件，不需要重复复制到工程中。
  - 原项目中所需要的jar包都是提前下载好的，而Maven在联网状态下会自动下载所需要的jar包。首先在本地仓库中寻找，如失败则在网上进行下载。
  - 原项目中一个jar包所依赖的其他jar包必须手动导进来，而Maven会自动将被依赖的jar包导入。
  - 原项目一个项目就是一个工程，而借助Maven可以将其拆分成多个工程。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%872.png?raw=true)

- 使用JWT进行身份验证

  JWT是一种基于token的认证机制，它类似于HTTP协议一样是无状态的，不需要在服务端保留用户的认证信息或者会话信息。

  除此之外，基于token的鉴权机制不需要考虑用户在哪一台服务器登录，为应用扩展提供了便利。

  本项目中，首先在登录阶段，后端为该用户自动生成一个token，发送给用户。用户将信息保存至LocalStorage中，并在之后将token放入请求头中。后端收到请求后，通过拦截器先取出请求头中的token，并根据token查询用户信息，然后将用户信息放入ThreadLocal中，便于后续使用用户信息。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%873.png?raw=true)

- 统一的异常处理

  开发过程中，难免有程序会因为某些原因抛出异常，而这些异常一般利用try …catch的方式处理异常或者throw的方式抛出异常。这种方法对于开发来说处理比较麻烦，对用户也不太友好，所以通过使用全局异常处理的方式方便程序员编写代码，不必过多处理各种异常编写重复的代码又能提升用户的体验。

  在本项目中，自定义了异常类GlobalExceptionHandler，并通过@ControllerAdvice注解用来开启全局的异常捕获，使用@ExceptionHandler说明捕获了哪些异常并对这些异常进行处理。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%874.png?raw=true)

- 统一的返回结果

  统一返回值类型是[接口开发](https://so.csdn.net/so/search?q=接口开发&spm=1001.2101.3001.7020)中的一种良好的开发习惯，大部分实际业务开发中会采用统一返回值。统一接口返回值的优点主要有以下两个：

  - 第一，可以节省前后端的沟通时间，前端默认后端接口返回的都是同一种结构；
  - 第二，接口有较好的可读性，干净整洁，易于形成良好的写代码习惯。

  于后端而言，所有接口返回值类型统一，有利于代码规范，并且对于前端而言，后端统一返回值，前端无需写不同代码来处理不同的返回结果，只需写一段统一的处理返回值的代码。本项目自定义返回结果类Result，利于代码整洁易读，方便协作开发。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%875.png?raw=true)

- Redis数据库缓存热点数据

  Redis缓存具有以下优点：

  -  Redis可以将数据全部存储在内存中，访问速度非常快，因此可以有效降低访问延迟。
  - Redis支持多种数据结构，可以存储不同类型的数据对象，例如字符串、列表、哈希表、集合等。
  - Redis是单线程的，避免了多线程并发时的复杂性和竞争条件。

  本项目后端配置了RedisTemplate操作redis数据库，将一些热点数据，如用户信息、商品信息存入redis，以此提高查询速度。

  在用户查询过程中，后端会先去redis里查询信息，若有则返回，若没有则再去mysql中查，查到后存入redis，然后返回，该过程有利于提高热点数据的更新速度。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%876.png?raw=true)

- 权限管理

  本项目中对相关权限进行管理，有利于功能的分配使用以及业务的顺利进行。部分细节如下：

  - 首先通过token拦截器，在一些controller上验证请求中是否携带token以及token是否合法。

  - 自定义一个注解@Authority，注解可以加在类上和方法上，限定该类或者方法的请求权限。

  - 定义一个拦截器，判断映射方法是否加有该注解。若有注解，则判断用户是否有对应权限。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%877.png?raw=true)

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%878.png?raw=true)

- 防止上传相同文件

  为防止用户上传相同文件，后端会先判断该文件的md5在数据库中是否已存在，若存在则不接收文件，直接使用已存在文件的url。该方法有效避免了数据库后台因重复图片造成的存储损失，提高了查询效率。

![](https://github.com/WoGiaoA/MajorPractice/blob/photos/%E5%9B%BE%E7%89%879.png?raw=true)


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
