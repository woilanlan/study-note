# SSL证书

[P12,JKS,CER,RFX,PEM转换速记](https://www.cnblogs.com/cherrychen-cakuta/p/8028020.html)

[将jks文件转化cer文件](https://www.jianshu.com/p/b79c4464cb51)

```log
1.keytool -list -v -keystore my.jks
2.输入密钥库口令
3.找到“别名”
4.keytool -export -alias 别名 -keystore amy.jks -storepass 密钥库口令 -file scert.cer
5.将证书导入到TrustStore文件中
keytool -import -file src_cer_file –keystore dest_cer_store（lib/security/）
```

[jks和cer文件生成](https://blog.csdn.net/lw_jack/article/details/85262627)

[jks转p12、keystore、pk8、x509.pem](https://www.jianshu.com/p/00693dfb7f31)

jks转p12：

```sh
keytool -importkeystore -srckeystore 要转换的.jks -destkeystore 转换后的.p12 -srcstoretype JKS -deststoretype PKCS12 -srcstorepass STORE密码 -deststorepass STORE密码 -srcalias 用户名 -destalias 用户名 -srckeypass KEY密码 -destkeypass KEY密码 -noprompt
```

p12转keystore

```sh
keytool -v -importkeystore -srckeystore 要转换的.p12 -srcstoretype PKCS12 -destkeystore 转换后的.keystore -deststoretype JKS
```

[P12,JKS,CER,RFX,PEM转换速记](https://blog.csdn.net/ONLYMETAGAIN/article/details/78782056)

[命令行生成自己的keystore](https://blog.csdn.net/micotale/article/details/80577892)
