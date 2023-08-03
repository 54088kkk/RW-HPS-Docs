## 协议的覆盖

在每一个 @MainProtocolImplementation 注解下的协议主实现 都会允许继承  
那么您可以继承 GameVersionServer GameVersionRelay等

### 例子

**请先设置Plugin在协议后加载**

```
/*
* Copyright 2020-2022 Dr.
*
*  此源代码的使用受 GNU AFFERO GENERAL PUBLIC LICENSE version 3 许可证的约束, 可以在以下链接找到该许可证.
*  Use of this source code is governed by the GNU AGPLv3 license that can be found through the following link.
*
*  https://github.com/RW-HPS/RW-HPS/blob/master/LICENSE
*/
package dr.rwhps.plugin.test;

/**
 * @author RW-HPS/Dr
 */
public class OveMain extends GameVersionServer {
    ...
    //在这里你可以干许多更有趣的事情
    // 覆盖部分实现
}
```

----