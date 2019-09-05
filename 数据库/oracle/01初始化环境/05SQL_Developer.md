# SQL Developer

安装64位版本Oracle 11g R2后发现启动SQL Developer时弹出配置java.exe的路径，在oracle安装目录$ORACLE_HOME\jdk\找到Oracle自带的java.exe后却弹出错误信息：

```log
Unable to find a java Virtual Machine to point to a location of a java virtual machine,
please refer to the oracle9i Jdeveloper Install guide(jdev\install.html)
```

安装路径：D:\Oracle\longlong\Oracle\product\11.2.0\dbhome_1\sqldeveloper\sqldeveloper\bin

由于没有重新配置的机会，到oracle安装目录$ORACLE_HOME\sqldeveloper\sqldeveloper\bin中找到配置文件sqldeveloper.conf，修改其中"SetJavaHome"项为"SetJavaHome C:\Program Files\Java\jdk1.6.0_21"，本机安装的JDK，结果还是一样。

Oracle在制造64位版的时候没注意Oracle 11g R2所带的SQL Developer是1.5.5.59.69版，不支持64位版本的JDK

解决：

官网下载最新版的SQL Developer

- 下载SQL Developer 18.4的Windows 64-bit with JDK 8 included版
- 解压后替换掉“product\11.2.0\dbhome_1”下的sqldeveloper文件夹
- 然后直接双击“sqldeveloper.exe”，运行成功

下载地址：<https://www.oracle.com/technetwork/developer-tools/sql-developer/downloads/index.html>

把“sqldeveloper.exe”的快捷方式复制到“C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Oracle - OraDb11g_home1\应用程序开发”下，即可从“开始”菜单打开“SQL Developer”。
