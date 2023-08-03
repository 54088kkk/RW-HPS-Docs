# RW-HPS - SaveData API

## Plugin保存数据

### 设计目标

- 源码级静态强类型：避免 `getString()`, `getList()`...
- 全自动加载保存：插件仅需在启动时通过一行代码链接自动保存
- 与前端同步修改：在 Android 等图形化前端实现中可以在内存动态同步修改
- 存储扩展性：可使用多种方式存储，无论是文件还是数据库，插件层都使用同一种实现方式

综上，**最小化插件作者在处理数据和配置做的付出**。

*暂无数据库保存支持，但这已经被提上日程。*

## [`Value`]

```java
interface Value<T> {
    private T data;
    
    protected Value(T data) {
        this.data = data;
    }
}
```

表示一个值代理。在 [`PluginData`] 中，值都经过 [`Value`] 包装。

## [`PluginData`]

一个插件内部的, 对用户隐藏的数据对象。类似于属性名作为键，对应 [`Value`] 作为值的 `Map`。

[`PluginData`] 接口拥有一个基础实现类，[`AbstractPluginData`]，默认不支持自动保存，仅存储键值关系及其序列化器。

插件可继承 [`AbstractPluginData`]，拥有高自由的实现细节访问权限，并扩展数据结构。  
但通常，插件使用 [`AutoSavePluginData`]。

[`AutoSavePluginData`] 监听保存在它之中的值的修改，并在合适的时机在提供的 [`AutoSavePluginDataHolder`] 协程作用域下启动协程保存数据。

### 使用 `PluginData`

示例在此时比理论更高效

1. 插件自己创建

```java
public class Main extends Plugin {
    PluginData pluginData = new PluginData();

    /**
     * 这里主要做初始化
     */
    @Override
    public void init() {
        // this.pluginDataFileUtil 是 继承Plugin后自动生成
        // 设置Bin文件位置
        pluginData.setFileUtil(this.pluginDataFileUtil.toFile("ExampleData.bin"));
        pluginData.read();

        // 读取
        long lastStartTime = this.pluginData.getData("lastStartTime", Time.concurrentMillis());
        String lastStartTimeString = this.pluginData.getData("lastStartTimeString", Time.getUtcMilliFormat(1));
        // 写入
        this.pluginData.setData("lastStartTime", Time.concurrentMillis());
        this.pluginData.setData("lastStartTimeString", Time.getUtcMilliFormat(1));
    }
}
```