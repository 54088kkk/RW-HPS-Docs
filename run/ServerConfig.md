# 配置服务器

RW-HPS提供了**3**个配置文件  
[Config.json](Config.md)为共用  
[ServerConfig.json](ServerConfig.md)为Server模式配置  
[ConfigRelay.json](ConfigRelay.md)为Relay模式配置  
注意: RW-HPS**不支持**热重载配置,每次修改配置请先关闭服务器!

## ServerConfig.json

### enterAd

> 进入消息(str)  

玩家进入时服务器发送给玩家的消息  
默认**未配置**

### startAd

> 开始消息(str)  

游戏开始时服务器发送给玩家的消息  
默认**未配置**

### maxPlayerAd

> 满员消息(str)  

进入服务器时,服务器已满员时拒绝玩家进入的消息  
默认**未配置**

### startPlayerAd

> 已开始消息(str)  

进入服务器时,服务器已开始游戏时拒绝玩家进入的消息  
默认**未配置**

### passwd

> 服务器密码(str)  

给服务器设置密码,所有玩家进入服务器时需要输入密码才能进入  
未配置则不设置密码
默认**未配置**

### maxPlayer

> 最大玩家数(int)  

设置服务器所能容纳的最大玩家数  
默认配置为**10**

### maxGameIngTime

> 最长游戏时间(int)  

设置游戏运行的时间,若达到设定的时间,则关闭此房间(不关闭服务器)  
配置为`-1`时则无限制  
单位: 秒(sec)  
默认配置为**7200**

### maxOnlyAIGameIngTime

> 没有其他玩家的最长游戏时间(int)  

当服务器只有AI时(也就是只有一群AI),若到达设定的时间,则关闭此房间(不关闭服务器)  
配置为`-1`时则无限制  
单位: 秒(sec)  
默认配置为**3600**

### startMinPlayerSize

> 最小开始人数(int)  

服务器开始游戏所需的最小人数  
配置为`-1`则无限制  
默认配置为**无限制**

### autoStartMinPlayerSize

> 自动开始人数(int)  

当服务器人数大于或等于(≥)此配置项时,服务器将自动开始游戏  
配置为`-1`则禁用此功能  
默认配置为**4**

### maxMessageLen

> 最大发言长度(int)  

服务器所允许的最大发言长度  
默认配置为**40**

### maxUnit

> 最大单位数量(int)  

服务器所允许的最大单位数量  
默认配置为**200**

### defIncome

> 默认倍率(float)  

服务器默认资金倍率(支持小数)  
默认配置为**1.0**

### turnStoneIntoGold

> 点石成金(bool)  

字面意思  
建筑单位*不需要*时间并且*不需要*资金  
默认配置为**禁用**

### oneAdmin

> 将第一个进入的玩家设置为管理员(bool)  

服务器将第一个进入服务器的玩家设置为管理员  
默认配置为**启用**

### saveRePlayFile

> 保存RePlay文件(bool)  

服务器允许客户端保存RePlay文件用于回放游戏过程  
默认配置为**启用**
