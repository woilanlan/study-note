# maven补充

1、创建一个webapp项目在Generating project in Interactive mode卡住

cmd /c mvn archetype:generate -DarchetypeArtifactId="maven-archetype-webapp" -DarchetypeGroupId="org.apache.maven.archetypes" -DgroupId="com.longlong" -DartifactId="webapp" -Dpackage="com.longlong.webapp" -DarchetypeCatalog=internal

cmd /c mvn archetype:generate -DarchetypeArtifactId="maven-archetype-quickstart" -DarchetypeGroupId="org.apache.maven.archetypes" -DgroupId="com.longlong" -DartifactId="spring" -Dpackage="com.longlong.spring" -DarchetypeCatalog=internal

2、package、install、deploy的区别

查看输出可知：

- mvn clean package依次执行了clean、resources、compile、testResources、testCompile、test、jar(打包)等７个阶段。
- mvn clean install依次执行了clean、resources、compile、testResources、testCompile、test、jar(打包)、install等8个阶段。
- mvn clean deploy依次执行了clean、resources、compile、testResources、testCompile、test、jar(打包)、install、deploy等9个阶段。

由上面的分析可知主要区别如下:

- package命令完成了项目编译、单元测试、打包功能，但没有把打好的可执行jar包（war包或其它形式的包）布署到本地maven仓库和远程maven私服仓库
- install命令完成了项目编译、单元测试、打包功能，同时把打好的可执行jar包（war包或其它形式的包）布署到本地maven仓库，但没有布署到远程maven私服仓库
- deploy命令完成了项目编译、单元测试、打包功能，同时把打好的可执行jar包（war包或其它形式的包）布署到本地maven仓库和远程maven私服仓库

3、maven项目警告：The compiler compliance specified is 1.7 but a JRE 1.8 is used

解决：

```xml
<properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
</properties>
```

修改maven项目使用的jdk版本的两种方式：
<https://blog.csdn.net/qq_36819098/article/details/79984716>

4、VScode中配置Maven

[学习笔记——Maven settings.xml 配置详解](https://www.cnblogs.com/zz0412/p/Maven_settings.html)

"java.configuration.maven.userSettings": null

[VsCode搭建springboot 并配置maven环境](https://blog.csdn.net/zhanaolu4821/article/details/84873312)

配置Maven：

点左下角的设置图标->设置，在设置内容筛选框输入：maven

"java.configuration.maven.userSettings": "D:\\apache-maven-3.3.3\\conf\\settings.xml"

5、查看maven依赖：

[查找maven项目](https://search.maven.org/)

[查找maven项目](https://mvnrepository.com/)
