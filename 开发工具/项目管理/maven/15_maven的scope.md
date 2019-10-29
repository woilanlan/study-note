# Maven Dependency scope

参考：

<https://uule.iteye.com/blog/2087485>

Dependency scope 是用来限制Dependency的作用范围的, 影响maven项目在各个生命周期时导入的package的状态。

## 共有了6种scope

### compile

默认的scope，表示 dependency 都可以在生命周期中使用。而且，这些dependencies 会传递到依赖的项目中。

### provided

跟compile相似，但是表明了dependency 由JDK或者容器提供，例如Servlet AP和一些Java EE APIs。这个scope 只能作用在编译和测试时，同时没有传递性。

使用这个时，不会将包打入本项目中，只是依赖过来。

使用默认或其他时，会将依赖的项目打成jar包，放入本项目的Lib里

```xml
<dependency>  
    <groupId>javax.servlet</groupId>  
    <artifactId>servlet-api</artifactId>  
    <version>2.5</version>  
    <scope>provided</scope>  
</dependency>  
<dependency>  
    <groupId>javax.servlet.jsp</groupId>  
    <artifactId>jsp-api</artifactId>  
    <version>2.1</version>  
    <scope>provided</scope>  
</dependency>
```

### runtime

表示dependency不作用在编译时，但会作用在运行和测试时

### test

表示dependency作用在测试时，不作用在运行时。

### system

跟provided 相似，但是在系统中要以外部JAR包的形式提供，maven不会在repository查找它。

```xml
<dependencies>
　　<dependency>
　　　<groupId>javax.sql</groupId>
　　　<artifactId>jdbc-stdext</artifactId>
　　　<version>2.0</version>
　　　<scope>system</scope>
　　　<systemPath>${java.home}/lib/rt.jar</systemPath>
　　</dependency>
</dependencies>
```

### import (Maven 2.0.9 之后新增)

它只使用在```<dependencyManagement>```中，表示从其它的pom中导入dependency的配置

```xml
<project>
<modelVersion>4.0.0</modelVersion>
<groupId>maven</groupId>
<artifactId>B</artifactId>
<packaging>pom</packaging>
<name>B</name>
<version>1.0</version>

<dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>maven</groupId>
        <artifactId>A</artifactId>
        <version>1.0</version>
        <type>pom</type>
        <scope>import</scope>
      </dependency>
    </dependencies>
</dependencyManagement>
</project>
```

B项目导入A项目中的包配置
