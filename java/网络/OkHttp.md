# OkHttp入门

1、添加maven依赖

```xml
<dependency>
    <groupId>com.squareup.okhttp3</groupId>
    <artifactId>okhttp</artifactId>
    <version>3.6.0</version>
</dependency>
```

2、代码

```java
package com.longlong;

import okhttp3.*;

import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.util.concurrent.TimeUnit;

public class DownloadImg {
    public static void main(String[] args) {
        //下载一张图片
        OkHttpClient.Builder builder = new OkHttpClient.Builder();
        builder.readTimeout(5, TimeUnit.SECONDS)
                .connectTimeout(5, TimeUnit.SECONDS);
        OkHttpClient okHttpClient = builder.build();

        Request.Builder requestBuilder = new Request.Builder();
        Request request = requestBuilder.url("http://pic1.win4000.com/wallpaper/c/53cdd1f7c1f21.jpg").get().build();
        okHttpClient.newCall(request).enqueue(new Callback() {
            public void onFailure(Call call, IOException e) {

            }

            public void onResponse(Call call, Response response) throws IOException {
                if (response.isSuccessful()) {
                    //如果请求成功
                    InputStream is = response.body().byteStream();
                    FileOutputStream fos = new FileOutputStream(new File("D:\\","111.jpg"));
                    byte[] buf = new byte[1024];
                    int len = 0;
                    while ((len = is.read(buf))!=-1){
                        fos.write(buf,0,len);
                        fos.flush();
                    }
                    fos.close();
                    is.close();
                }
            }
        });
    }
}
```

3、在spring中注入OkHttpClient，要使用静态工厂创建

静态工厂

```java
package com.longlong;

import okhttp3.OkHttpClient;

import java.util.concurrent.TimeUnit;

public class OkHttpClientUtils {
    public static OkHttpClient getInstance(){
        return new OkHttpClient.Builder()
                .connectTimeout(5, TimeUnit.SECONDS)
                .readTimeout(5,TimeUnit.SECONDS)
                .build();
    }
}
```

配置Bean

```xml
<bean id="okHttpClient" class="com.longlong.OkHttpClientUtils" factory-method="getInstance"></bean>
```

获取Bean

```java
ClassPathXmlApplicationContext ctx = new ClassPathXmlApplicationContext("applicationContext.xml");
OkHttpClient okHttpClient = (OkHttpClient) ctx.getBean("okHttpClient");
```
