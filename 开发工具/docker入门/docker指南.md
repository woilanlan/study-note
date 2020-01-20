# docker指南

官网：<https://www.docker.com/>

进入官网，点击“Get Started”,点击“Download Desktop for Mac and Windows”

注册一个docker账号，并且登录，进行下载

网址：<https://hub.docker.com/?overlay=onboarding>

1、点击“Download Docker Desktop for Windows”下载安装包，进行安装

2、下载演示的存储库

这个仓库包含了创建自己第一个容器需要的所有东西

前提：本机上已安装了git

打开命令行，移动到想要保存的位置，执行以下命令

```log
git clone https://github.com/docker/doodle.git
```

3、现在让我们构建并标记一个Docker映像。

Docker映像是专用的文件系统，只用于您的容器。它提供容器需要的所有文件和代码。

运行docker构建命令使用Dockerfile创建一个docker映像，这个构建的映像位于机器的本地docker映像注册表中。

```log
cd doodle\cheers2019

docker build -t woilanlan/cheers2019 .
```

4、运行你的第一个容器。

运行容器会启动带有私有资源的软件。安全地与机器的其余部分隔离。

```log
docker run -it --rm woilanlan/cheers2019
```

5、在Docker Hub上共享您的映像

```log
docker login
docker push woilanlan/cheers2019
```
