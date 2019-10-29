# svn项目更换地址

[svn项目更换地址](https://knight-black-bob.iteye.com/blog/2306343)

1、保存原始路径，右击properties -> svn 版本控制

[原始url](http://127.0.0.1/opp/PrecisionLAB/07MavenSrc/TRACEMonitor/trunk)

2、右击team -> 断开连接，删除所有svn元信息

3、新建资源地址，在svn资源库中，右击 –> 新建 –> 资源库位置

4、添加新的路径，修改对应IP地址（指定到项目文件夹的上一级）

[现在url](http://127.0.0.2/opp/PrecisionLAB/07MavenSrc/TRACEMonitor)

5、绑定新svn路径

右击项目 –> team -> share project -> svn -> 选择之前创建的路径 –> 使用指定项目名(之前是trunk) -> 添加注释
