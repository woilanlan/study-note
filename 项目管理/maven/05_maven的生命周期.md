# maven的生命周期

## 编译：mvn compile

生成target目录：

- classes

不编译Test目录下的文件

```log
D:\java\longlong\day46_00_mavenHello>mvn compile
[INFO] Scanning for projects...
[INFO]
[INFO] -------------------------< com.itheima:Hello >--------------------------
[INFO] Building Hello 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ Hello ---
[INFO] Changes detected - recompiling the module!
[WARNING] File encoding has not been set, using platform encoding GBK, i.e. build is platform dependent!
[INFO] Compiling 1 source file to D:\java\longlong\day46_00_mavenHello\target\classes
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  3.317 s
[INFO] Finished at: 2019-03-04T16:59:10+08:00
[INFO] ------------------------------------------------------------------------
```

## 清理：mvn clean

```log
D:\java\longlong\day46_00_mavenHello>mvn clean
[INFO] Scanning for projects...
[INFO]
[INFO] -------------------------< com.itheima:Hello >--------------------------
[INFO] Building Hello 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ Hello ---
[INFO] Deleting D:\java\longlong\day46_00_mavenHello\target
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.902 s
[INFO] Finished at: 2019-03-04T17:01:08+08:00
[INFO] ------------------------------------------------------------------------
```

## 测试：mvn test

生成target目录：

- classes：存放编译后的类
- maven-status
- surefire-reports:存放测试报告
- test-classes：存放编译后的测试类

只要进行测试，清理和编译可以自动执行了。

```log
D:\java\longlong\day46_00_mavenHello>mvn test
[INFO] Scanning for projects...
[INFO]
[INFO] -------------------------< com.itheima:Hello >--------------------------
[INFO] Building Hello 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ Hello ---
[INFO] Changes detected - recompiling the module!
[WARNING] File encoding has not been set, using platform encoding GBK, i.e. build is platform dependent!
[INFO] Compiling 1 source file to D:\java\longlong\day46_00_mavenHello\target\classes
[INFO]
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ Hello ---
[INFO] Changes detected - recompiling the module!
[WARNING] File encoding has not been set, using platform encoding GBK, i.e. build is platform dependent!
[INFO] Compiling 1 source file to D:\java\longlong\day46_00_mavenHello\target\test-classes
[INFO]
[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ Hello ---
[INFO] Surefire report directory: D:\java\longlong\day46_00_mavenHello\target\surefire-reports

-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running com.itheima.maven.HelloTest
Tests run: 0, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 sec

Results :

Tests run: 0, Failures: 0, Errors: 0, Skipped: 0

[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  5.320 s
[INFO] Finished at: 2019-03-04T17:02:02+08:00
[INFO] ------------------------------------------------------------------------
```

## 打包：mvn package

生成target目录下生成jar包：Hello-0.0.1-SNAPSHOT.jar

```log
D:\java\longlong\day46_00_mavenHello>mvn package
[INFO] Scanning for projects...
[INFO]
[INFO] -------------------------< com.itheima:Hello >--------------------------
[INFO] Building Hello 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ Hello ---
[INFO] Changes detected - recompiling the module!
[WARNING] File encoding has not been set, using platform encoding GBK, i.e. build is platform dependent!
[INFO] Compiling 1 source file to D:\java\longlong\day46_00_mavenHello\target\classes
[INFO]
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ Hello ---
[INFO] Changes detected - recompiling the module!
[WARNING] File encoding has not been set, using platform encoding GBK, i.e. build is platform dependent!
[INFO] Compiling 1 source file to D:\java\longlong\day46_00_mavenHello\target\test-classes
[INFO]
[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ Hello ---
[INFO] Surefire report directory: D:\java\longlong\day46_00_mavenHello\target\surefire-reports

-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running com.itheima.maven.HelloTest
Tests run: 0, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 sec

Results :

Tests run: 0, Failures: 0, Errors: 0, Skipped: 0

[INFO]
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ Hello ---
[INFO] Building jar: D:\java\longlong\day46_00_mavenHello\target\Hello-0.0.1-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  5.682 s
[INFO] Finished at: 2019-03-04T17:19:05+08:00
[INFO] ------------------------------------------------------------------------
```

## 部署：mvn clean install

把jar包部署到本地仓库中

```log
D:\java\longlong\day46_00_mavenHello>mvn install
[INFO] Scanning for projects...
[INFO]
[INFO] -------------------------< com.itheima:Hello >--------------------------
[INFO] Building Hello 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ Hello ---
[INFO] Nothing to compile - all classes are up to date
[INFO]
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ Hello ---
[WARNING] Using platform encoding (GBK actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ Hello ---
[INFO] Nothing to compile - all classes are up to date
[INFO]
[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ Hello ---
[INFO] Surefire report directory: D:\java\longlong\day46_00_mavenHello\target\surefire-reports

-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running com.itheima.maven.HelloTest
Tests run: 0, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.019 sec

Results :

Tests run: 0, Failures: 0, Errors: 0, Skipped: 0

[INFO]
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ Hello ---
[INFO]
[INFO] --- maven-install-plugin:2.4:install (default-install) @ Hello ---
[INFO] Installing D:\java\longlong\day46_00_mavenHello\target\Hello-0.0.1-SNAPSHOT.jar to D:\java\course\maven\mavenRepository\com\itheima\Hello\0.0.1-SNAPSHOT\Hello-0.0.1-SNAPSHOT.jar
[INFO] Installing D:\java\longlong\day46_00_mavenHello\pom.xml to D:\java\course\maven\mavenRepository\com\itheima\Hello\0.0.1-SNAPSHOT\Hello-0.0.1-SNAPSHOT.pom
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  19.515 s
[INFO] Finished at: 2019-03-04T20:39:06+08:00
[INFO] ------------------------------------------------------------------------
```
