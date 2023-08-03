# 配置服务器

RW-HPS提供了**3**个配置文件  
[Config.json](Config.md)为共用  
[ServerConfig.json](ServerConfig.md)为Server模式配置  
[ConfigRelay.json](ConfigRelay.md)为Relay模式配置  
注意: RW-HPS**不支持**热重载配置,每次修改配置请先关闭服务器!

## ConfigRelay.json

### mainID

> 前置ID(str)  

Relay模式下的房间前置ID  
未配置的话默认只有数字  
默认**未配置**

### mainServer

> 是否是 RELAY 主节点(bool)  

主节点将可以分配分节点分ID, 例如
RCN 分配 RA, 那么如果是 true, RA就会被跳转, 如果是 false, 就会解析

默认配置为**启用**

### upList

> TODO(bool)  

服务器是否支持 uplist
默认配置为**禁用**

### mainServerIP

> TODO(str)  



### mainServerPort

> TODO(int)  




> 什么?你问我为什么是`TODO`?  
> 其实我也不知道为什么是`TODO`呀  
> ~~也许是Dr太懒了吧~~
