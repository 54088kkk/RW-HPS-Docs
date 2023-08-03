# RW-HPS - UserManual

RW-HPS 用户手册  
本文面向对开发不熟悉而希望使用 RW-HPS 的用户。如果你要开发，请先阅读 [开发文档](/plugin/README.md)

## 使用纯控制台版本 启动 RW-HPS

### 安装

* [直接运行](/run/Run.md)
* [使用Docker容器](/docker/README.md)

### 了解运行环境

第一次运行会初始化运行环境。下表说明了各个文件夹的用途。

Config配置解释 : [服务器配置](Config.md)

|             文件夹名称             | 用途                               |
|:----------------------------------:|:-----------------------------------|
|        `data/plugins`         | 存放插件                                |
|          `data/maps`          | 存放地图                                |
|          `data/mods`          | 存放Rwmod                               |
|         `data/cache`          | 存放缓存，一般不需要在意它们            |
|          `data/libs`          | 存放依赖，一般不需要在意它们            |
|        `data/CoreLib`         | 存放Hess核心依赖，一般不需要在意它们    |
|          `data/log`           | 存放Log，一般不需要在意它们             |
|      `data/Config.json`       | 存放服务器配置，可以打开并修改配置      |
|    `data/ConfigServer.json`   | 存放处于Server模式时的服务器配置        |
|     `data/RelayConfig.json`   | 存放处于Relay模式时的服务器配置         |
|       `data/Test.json`        | 存放测试选项                            |
|      `data/Settings.bin`      | 存放内部配置，一般不需要在意它们        |

### 下载和安装插件

刚刚装好的 RW-HPS 是没有任何自定义功能的。功能将由插件提供。

### 使用Mod

把mod扔进 `data/mods` 就好了 !

### 使用地图

#### 自定义地图

把地图扔进 `data/maps` , 然后参阅[怎么切换地图](#怎么切换地图)

#### 使用保存的游戏

把文件后缀改为 `.save` 扔进 `data/maps` , 然后参阅[怎么切换地图](#怎么切换地图)

#### 怎么切换地图

在客户端聊天框输入 `.maps` 你就可以查看到服务器生效的地图  
同时你可以在每个名字前发现一个 数字ID  
在客户端聊天框输入 `.map+空格+ID` 你就可以切换到你的自定义地图  
**注意 切换地图后房主的地图显示可能会有问题 是正常的 不需要动**  
**如果需要切回原版 那么在房主的原版地图挑一个就好了**

## 解决问题

如果遇到使用问题或想提建议，可以在  
[issues](https://github.com/RW-HPS/RW-HPS/issues)  
[Tencent QQ群](https://qm.qq.com/cgi-bin/qm/qr?k=qhJ6ekYF9pD9jO6j8H2rZw8ePAVypoU0&jump_from=webapi)  
<del>[Telegram组](https://t.me/RW_HPS) </del>  
[DisCord组](https://discord.gg/VwwxJhVG64)

进行发表和讨论