# java相关

1、警告："Classpath is incomplete" warning

现象：在创建单个java文件，或者从Maven原型生成的工程，在打开java文件提示这个类路径不完整。

原因：的maven项目不在工作空间的根目录。

解决：

- 打开一个完整的Eclipse文件或者Maven项目文件。
- 移除项目所在的文件夹，重新把项目添加到工作区。

2、maven项目警告：The compiler compliance specified is 1.7 but a JRE 1.8 is used

现象：pom文件对应的java编译环境为1.7,但是java运行环境为1.8

解决：

```xml
<properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
</properties>
```

3、选择maven的配置文件

点左下角的设置图标->设置，在设置内容筛选框输入：maven

"java.configuration.maven.userSettings": "D:\\apache-maven-3.3.3\\conf\\settings.xml"

4、从Maven原型生成一个webapp项目在Generating project in Interactive mode卡住

cmd /c mvn archetype:generate -DarchetypeArtifactId="maven-archetype-webapp" -DarchetypeGroupId="org.apache.maven.archetypes" -DgroupId="com.longlong" -DartifactId="webapp" -Dpackage="com.longlong.webapp" -DarchetypeCatalog=internal

cmd /c mvn archetype:generate -DarchetypeArtifactId="maven-archetype-quickstart" -DarchetypeGroupId="org.apache.maven.archetypes"
-DgroupId="com.longlong" -DartifactId="logintest" -Dpackage="com.longlong.logintest" -DarchetypeCatalog=internal

5、运行Java Web项目

- 安装插件：Tomcat for java
- 在资源管理器会多一栏Tomcat Servers
- 点击加号，选择Tomcat的文件路径，即可添加成功。
- 显示所有命令：Ctrl + Shift + P
- 输入：Tomcat:Generate War Package from Current Folder
- 选择对应项目文件夹，即可生成对应的war包
- 在war包上右键，选择Run on Tomcat Servers

6、vscode 导入第三方jar包（添加外部JAR）

<https://www.cnblogs.com/yunyun520/p/11120681.html>

添加 jar包 至根目录下lib文件夹，在 .classpath 文件内添加 jar 路径。

7、使用 VS Code 打造 Java 开发环境

<https://somelogs.com/article/vscode-java>

项目中如果有自己 install 的包或者公司私服的包

vscode 这个 maven 插件从来就不会读取 java.* 开头的配置，所以这个配置没有生效。

"java.configuration.maven.userSettings": "E:\\file\\jar\\mvn-repository\\settings.xml"

使用配置 maven.executable.options 来指定 settings.xml

"maven.executable.options": "-s E:\\file\\jar\\mvn-repository\\settings.xml"
