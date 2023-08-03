# 配置服务器
RW-HPS提供了**3**个配置文件  
[Config.json](Config.md)为共用  
[ServerConfig.json](ServerConfig.md)为Server模式配置  
[ConfigRelay.json](ConfigRelay.md)为Relay模式配置  
注意: RW-HPS**不支持**热重载配置,每次修改配置请先关闭服务器!

## Config.json

### defStartCommand
服务器默认启动命令(str)  
Server模式为**start**  
Relay模式为**startrelay**/**startrelaytest**
> startrelay 直接转发消耗更多带宽，效果与使用 VPN 转发相同  
> startrelaytest 使用多播, 减少宽带消耗

默认配置为**start**

### log
log记录等级(str)  
决定log记录的级别,通常级别越高输出内容越多  
> 输入错的则默认 ALL  
> OFF FATAL ERROR WARN INFO DEBUG TRACE ALL  

默认配置为**WARN**

### cmdTitle
终端标题(str)  
RW-HPS在启动完成时会更改终端标题  
在Windows上,使用native方法  
在Linux上,使用vt100控制符  
若未配置,则显示
> [RW-HPS] Port: 5123, Run Server: ${NetStaticData.ServerNetType.name}

默认**未配置**

### followBetaVersion
使用测试版本更新服务器(bool)  
RW-HPS支持在服务器控制台处更新服务器,只需输入`tryupdate`即可  
如果启用,则使用测试版本更新服务器,您会提前体验到新功能~~也会体验到新bug~~  
如果禁用,则使用稳定版更新服务器  
默认配置为**禁用**

### port
服务器端口(int)  
指定服务器所使用的端口  
默认配置为**5123**

### serverName
服务器名(str)  
服务器在列表处的服务器名  
默认配置为**RW-HPS**

### subtitle
地图名(str)  
服务器在列表处的地图名  
未配置则为地图名  
默认**未配置**

### autoUpList
自动上列表(bool)  
可以让服务器启动时自动上列表(相当于`uplist add`)  
默认配置为**禁用**

### ipCheckMultiLanguageSupport
基于IP判断多语言支持(bool)  
可以通过玩家IP判断玩家的国家从而对每个玩家都显示它的本国语言(前提是翻译文件有那个语言)  
默认配置为**禁用**

### singleUserRelay
Relay单用户模式(bool)  
类似与Relay模式,但是只有一个房间    
默认配置为**禁用**

### singleUserRelayMod
Relay单用户模式的mod支持(bool)  
为Relay单用户模式启用mod支持  
默认配置为**禁用**

### webToken
HttpApi令牌(str)  
此令牌在[HttpApi](/api/HttpAPI.md)处使用  
默认配置为**随机生成**

### webHOST
HTTP主机限制(str)  
限制HTTP的Host,防止从IP访问  
默认**未配置**

### webPort
HTTP服务器端口(int)  
指定HTTP服务器所使用的端口,`0`为禁用HTTP服务器  
注意: 现已**不支持**端口复用,请勿与游戏服务器设置同一端口  
默认配置为**禁用**

### ssl
启用HTTPS(bool)  
**不建议**使用SSL  
启用HTTP服务器的SSL(即HTTPS)
默认配置为**禁用**

### sslPasswd
SSL证书的密码(str)  
警告: **明文**密码  
要配置SSL,你需要在和jar同级的地方放置`ssl.jks`(大小写敏感)  
然后在此配置项输入JKS证书密码  
默认**未配置**

### runPid
服务器运行PID(int)  
你不需要知道这是干什么的,也不需要动它  
> 如果你想知道的话:  
> 提供当前 JVM 的 pid, 便于使用其他程序关闭 JVM
