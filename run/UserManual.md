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

**注意**: RW-HPS提供了3个配置文件,而不是只有`Config.json`！

|        文件夹名称        |      用途      |
| :----------------------: | :------------: |
|       `data/cache`       |      缓存      |
|       `data/libs`        |    依赖文件    |
|     `data/gameData`      | HESS 资源文件  |
|       `data/maps`        |    游戏地图    |
|       `data/mods`        |    游戏模组    |
|      `data/plugins`      |   服务器插件   |
|      `data/replays`      |   服务器回放   |
|        `data/log`        |   服务器日志   |
|    `data/Config.json`    | 服务器通用配置 |
| `data/ConfigServer.json` | Server模式配置 |
| `data/RelayConfig.json`  | Relay模式配置  |
|   `data/Settings.bin`    |    内部数据    |

### 下载和安装插件

刚刚装好的 RW-HPS 是没有任何自定义功能的哦！功能将由插件提供

通常情况下, 把插件扔进`data/plugins`就能用啦

### 使用Mod

把mod扔进 `data/mods` 就好了 !

后缀名必须为`rwmod`

**不要解压！** **不要解压！** **不要解压！**

~~重要的事情说三遍~~

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