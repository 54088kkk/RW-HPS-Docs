# RW-HPS - Net

**目录**

- [1. Net](#1-Net)
    - [创建Net](#创建Net)
        - [启动端口监听](#启动端口监听)
        - [修改协议](#修改协议)

## 1. Net

在服务器的启动中 服务器使用的是 [CoreCommand : startnetservice] 来启动的端口监听

### 创建Net

在服务器中 每个Port 或者是Port段 均是被StartNet描述  
服务器的核心即在这里

```kotlin
class StartNet {
    // 默认协议
    constructor()

    // 自定义协议
    constructor(abstractNetClass: Class<*>)
}
```

通常的调用方法为：

```kotlin
// Kotlin
val startNet = StartNet()
```

```java
// Java
StartNet startNet = StartNet();
```

#### 启动端口监听

```kotlin
val startNet = ~
startNet.openPort(主端口)
// 如果是监听多个端口 那么可以
startNet.openPort(主端口,监听范围起始,监听范围结束)
```

#### 修改协议

只需要继承AbstractNet即可修改 initChannel 实现, 来自定义协议  
在 `RW-HPS` 中 已经默认实现了一个GamePort共用解析器, 您可以自行调用

```kotlin
class NewShunt(startNet: StartNet) : AbstractNet(startNet) {
    override fun initChannel(socketChannel: SocketChannel) {
        // 发挥创造力
        socketChannel.pipeline().addLast()
    }
}
```