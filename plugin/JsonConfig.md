## Plugin的构成

```
jar
    └───[class]
    plugin.json        //Plugin的配置文件          
```

### Plugin.json解析

```
{
  "name": "Plugin的名字",
  "author": "Plugin的作者",
  "main": "Plugin的主Main",
  "description": "Plugin的介绍",
  "version": "Plugin的版本"，
  "supportedVersions": "Plugin可以支持加载的版本" (在1.3.0-M2+DEV以上)
  (可选)"import": "你要在谁的后面进行加载(名称)"
}
```

#### 正常的例子

```
{
"name": "NetConnectProtocol",
"author": "Dr",
"main": "dr.rwhps.plugin.netconnectprotocol.Main",
"description": "RustedwarfareServer 1.14 NetConnectProtocol",
"version": "1.14 - 1.2.0.1 +",
"supportedVersions": "> 1.3.0-M1"
}
```

#### 依赖加载的例子

##### 递归加载是什么

简称 需要前置插件
你可以发布一个公用Utils包 , 而其他Plugin开发者只需要依赖你的就可以

请注意 递归依赖只会递归一次 不会进行多次,这是为了防止CPU高占用

```
{
"name": "NetConnectProtocol-EX",
"author": "Dr",
"main": "dr.rwhps.plugin.netconnectprotocol.Main",
"description": "RustedwarfareServer 1.14 NetConnectProtocol",
"version": "1.14 - 1.2.0.1 +",
"import": "NetConnectProtocol"
}
```

#### supportedVersions的使用

**需要注意空格**

对于一条规则, 有以下方式可选

- `1.0.0-M4`       要求 1.0.0-M4 版本, 且只能是 1.0.0-M4 版本
- `> 1.0.0-RC`     要求 1.0.0-RC 之后的版本, 不能是 1.0.0-RC
- `>= 1.0.0-RC`    要求 1.0.0-RC 或之后的版本, 可以是 1.0.0-RC
- `< 1.0.0-RC`     要求 1.0.0-RC 之前的版本, 不能是 1.0.0-RC
- `<= 1.0.0-RC`    要求 1.0.0-RC 或之前的版本, 可以是 1.0.0-RC
- `!= 1.0.0-RC`    要求 除了1.0.0-RC 的任何版本
    - `[1.0.0, 1.2.0]`
    - `(1.0.0, 1.2.0]`
    - `[1.0.0, 1.2.0)`
    - `(1.0.0, 1.2.0)`  

[数学区间](https://baike.baidu.com/item/%E5%8C%BA%E9%97%B4/1273117)

特别注意:

- 依赖规则版本号不需要携带版本号元数据, 元数据不参与依赖需求的检查
- 如果目标版本号携带有先行版本号, 请不要忘记先行版本号
- **请注意空格**  