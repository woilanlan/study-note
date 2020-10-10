# gitlab问题

1、输入了错误的gitlab用户名和密码，导致无法推送到远程服务器

搜索 >> 凭据管理器 >> Windows凭据 >> 找到凭据```git:https://gitlab.com``` >> 删除 >> 重新push >> 弹框提示输入用户名和密码。

2、启用了双重身份验证后，创建个人访问令牌，它们是唯一接受的密码

点击用户头像 >> Settings >> Access Tokens >> 输入名称和有效期 >> 勾选 read_repository 和 write_repository >> 点击创建 >> 保存Access Token

[项目添加用户和权限管理](https://www.yiibai.com/gitlab/gitlab_introduction.html)

[GitLab 多人协同合作开发流程](https://www.jianshu.com/p/f57f08918a8b)

