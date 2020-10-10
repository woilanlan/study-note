# maven的准备工作

## Maven的安装与配置

### 1、下载并安装Java SE Development Kit（JDK）

配置环境变量JAVA_HOME设置为JDK的安装位置。并添加到PATH路径中

### 2、下载并安装Apache Maven

解压到任意目录，将其中的bin文件夹的路径添加到环境变量path中

下载地址：<https://maven.apache.org/download.cgi>
安装说明：<https://maven.apache.org/install>

```bat
//检查JAVA环境配置
echo %JAVA_HOME%
C:\Program Files\Java\jdk1.7.0_51

//配置
MAVEN_HOME
D:\java\base\apache-maven-3.6.0\bin

//添加到PATH
%MAVEN_HOME%

//验证是否配置成功
mvn -v
```

### 3、目录说明

bin：中存放可执行的二进制文件
conf：存放settings.xml文件
lib：运行maven所依赖的jar包

### 4、配置本地仓库

4.1 默认本地路径：有一个repository文件夹

```log
C:\Users\longlong\.m2
```

4.2 指定仓库的路径：

进入apache-maven-3.6.0\conf\目录，修改settings.xml配置文件，这里指定mavenRepository为仓库的路径

```xml
<!-- localRepository
| The path to the local repository maven will use to store artifacts.
|
| Default: ${user.home}/.m2/repository
<localRepository>/path/to/local/repo</localRepository>
-->

<localRepository>D:\java\course\maven\mavenRepository</localRepository>
```
