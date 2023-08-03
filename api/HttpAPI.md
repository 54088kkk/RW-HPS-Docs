# RW-HPS - Http API

> 注:
> - 本章节是介绍 `RW-HPS` 中的一个内置插件
> - 本章节**不是**关于 `UPLIST-API` 的章节

## 使用

要想使用HttpApi,你需要先使用`GET`方式请求`/HttpApi/api/AuthCookie`并携带参数`passwd`

默认密码是*随机生成*的,可在配置文件找到`webToken`查询

请求完成后会得到一个名为`HttpApi-Authentication`的cookie,有效期为**24小时**

之后每一次请求都**必须**携带此cookie,否则服务器会返回403

### GET

路径: `/HttpApi/api/get/xxx`

#### info

##### SystemInfo

路径: `/HttpApi/api/get/info/SystemInfo`(其他同理)

返回

```json
{
    "status": "OK",
    "data": "{\"system\":\"Linux\",\"arch\":\"amd64\",\"jvmName\":\"OpenJDK 64-Bit Server VM\",\"jvmVersion\":\"11.0.20\"}"
}
```

##### GameInfo

返回

```json
{
    "status": "OK",
    "data": "{\"income\":1.0,\"noNukes\":false,\"credits\":0,\"sharedControl\":false,\"players\":[]}"
}
```

##### ModsInfo

返回

```json
{
    "status": "OK",
    "data": "[\"RW-HPS CoreUnits\"]"
}
```

#### event

##### GameOver

返回

```json
{
    "status": "OK",
    "data": "[]"
}
```

### POST

路径: `/HttpApi/api/post/xxx`

#### run

##### ServerCommand

用处: *执行服务器命令,发送返回*

// TODO

##### ClientCommand

用处: *执行客户端命令,发送返回*

// TODO

### WebSocket

路径: `/WebSocket/HttpApi/api/Console`

每隔几秒客户端需要`ping`(下文可找到此方法),若在10秒内无操作,服务器将会以超时为由断开客户端连接

以下为可用操作

#### Register

用处: *在服务器中注册此cookie,参数使用上文所得到的cookie,注册完成后客户端无需继续携带此cookie*

发送

```json
{
    "cookie" : "5420dedf8f1829bc43d03843d26216523fe19e06ee253abcacd3a4ee5b9af12b",
    "type" : "register"
}
```

返回

```json
{
    "code": 200,
    "data": "Register OK"
}
```

#### Ping

用处: *保活*

发送

```json
{
    "type": "ping"
}
```

返回

```json
{
    "code": 200,
    "data": "pong"
}
```

#### GetConsole

用处: *将服务器控制台输入发送至ws直到客户端断开连接*

发送

```json
{
    "type": "getConsole"
}
```

返回

```json
{
    "code": 200,
    "data": "[9072-79-85 20:08:33] 这是一条不存在的日志"
}
```

#### RunCommand

用处: *运行服务器命令*

注: 要获取返回结果请先`getConsole`

发送

```json
{
    "type": "runCommand",
    "runCommand": "version"
}
```

返回

**无**

