# Chrome浏览器使用

问题：

1、chrome出现“由贵单位管理”原因及解决方法

谷歌Google在声明里表示：由贵单位管理指的是由设备或者账户管理员例如企业管理器可以用来强制更改谷歌浏览器配置的企业级策略。例如可以直接通过远程方式向所有受控用户添加书签，当管理员有进行这类操作时那么就会显示由单位管理。

主要阿里旺旺(千牛) 安装之后就会自动给chrome安装第三方扩展然后修改策略

手动发现问题元凶：

谷歌Chrome浏览器地址栏输入```chrome://policy```，即可看到调用企业策略的第三方软件或者是用户主动安装的第三方扩展等

解除赋予权限去除“由贵单位管理”功能选项

- windows系统按 Win + R 输入 RegEdit 运行注册表管理
- 删除注册表```\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome```所有项目和键值
- 浏览器地址栏输入```chrome://flags/#show-managed-ui```
- 把 Show managed UI for managed users 这个设置为 Disabled，并重启浏览器。
