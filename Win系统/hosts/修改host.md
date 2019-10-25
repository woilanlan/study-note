# 修改host文件

## 1、完美解决Github访问缓慢问题

国内访问 GitHub 为什么很慢？

GitHub的CDN域名遭到DNS污染，导致无法连接使用 GitHub 的加速分发服务器，才使得国内访问速度很慢。

如何解决 DNS 污染？

通过修改 Hosts 文件，将域名解析直接指向 IP 地址来绕过 DNS 的解析，以此解决污染问题。

解决步骤

1、访问<https://www.ipaddress.com/>获取github最新的ip地址

2、修改 host 文件

文件路径：C:\Windows\System32\drivers\etc\host

```log
140.82.113.4    github.com
199.232.5.194   github.global.ssl.fastly.net
99.84.240.40    d3c33hcgiwev3.cloudfront.net
```

3、更新dns缓存

```log
ipconfig /flushdns
```
