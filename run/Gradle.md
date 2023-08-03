# RW-HPS - Gradle

## Gradle

### Gradle 是什么

Gradle是一个基于Apache Ant和Apache Maven概念的项目自动化建构工具。它使用一种基于Groovy的特定领域语言来声明项目设置，而不是传统的XML。当前其支持的语言限于Java、Groovy和Scala，计划未来将支持更多的语言。

### Gradle 如何使用

1. Gradle 运行依赖 JVM，也就是 Java 运行的环境。所以要安装 JDK 和 JRE ,建议使用 Java11 ,因为 Java 可向下兼容
2. 然后到 Gradle 官网下载 Gradle 的压缩包。地址，这个页面里面又两种方式，一种手动安装，一种通过脚本安装。我一般喜欢自己动手，这样将来清理起来比较方便
3. 下载压缩包后，解压，然后配置环境变量，手动安装过 JDK 的人应该都配置环境变量很熟了吧。每个平台下配置环境变量的方式不一样

## 使用Gradle编译

### 初始

1. 打开终端  
   在您需要的目录下打开 Cmd or PowerShell
2. 开始编译  
   在命令行输入

```bash
./gwadlew jar
```

等待完毕即可

3.使用  
在目录 `Server-All/build/libs` 下即可获得编译好的Server Jar

**更多教程 请参阅 [Google](https://google.com) or [Baidu](https://baidu.com) or [Bing](https://bing.com)**