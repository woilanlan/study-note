# maven的继承

问题：在上一节中发现三个项目都依赖junit的jar包，每一个项目的pom.xml文件中都要进行依赖配置。

## 实例

1、新建Maven项目：day46_05_maven2Base

2、删除Source Folder文件夹

- src/main/java
- src/test/java

3、修改配置文件pom.xml

配置共用的依赖jar包，修改为pom打包方式，只会部署对应的pom.xml文件，并不会编译java类

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>com.itheima.maven2</groupId>
  <artifactId>Base</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <packaging>pom</packaging>

  <name>Base</name>
  <url>http://maven.apache.org</url>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  </properties>

  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.9</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
```

4、新建Maven项目：day46_06_maven2HelloBase，进行继承

pom.xml

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>com.itheima.maven2</groupId>
  <artifactId>HelloBase</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <packaging>jar</packaging>

  <name>HelloBase</name>
  <url>http://maven.apache.org</url>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  </properties>
  
  <parent>
    <groupId>com.itheima.maven2</groupId>
    <artifactId>Base</artifactId>
    <version>0.0.1-SNAPSHOT</version>
  </parent>

  <dependencies>
  </dependencies>
</project>
```

## 拓展了解

1、Shiro是一个强大易用的Java安全框架,提供了认证、授权、加密和会话管理等功能

参考：<http://www.cnblogs.com/learnhow/p/5694876.html>

2、Activiti是由Alfresco软件在2010年5月17日发布的业务流程管理(BPM)框架,它是覆盖了业务流程管理，工作流，服务协作等领域的一个开源，灵活的，易扩展的可执行流程语言框架。

官网：<https://www.activiti.org/>

使用入门：<https://activiti.gitbook.io/activiti-7-developers-guide/getting-started/getting-started-activiti-core>

参考：<https://blog.csdn.net/qq_29582193/article/details/79420787>

3、查找Maven项目的依赖：

<https://search.maven.org>

<https://mvnrepository.com/>
