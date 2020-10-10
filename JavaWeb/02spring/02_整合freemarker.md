# freemarker

xml方式配置：

[springMVC与freemarker的整合](https://www.cnblogs.com/jingbaober/p/5781987.html)

[SpringMVC使用Freemarker作为视图解析](https://blog.csdn.net/xiaoping0915/article/details/72814980)

[springMVC整合freemarker的使用](https://blog.csdn.net/maoyuanming0806/article/details/77886027)

java方式配置：

[SpringMVC Java config freemarker](https://www.cnblogs.com/magicdesign/p/3559967.html)

[freemaker中文乱码 springMVC框架中](https://blog.csdn.net/jimoshazhouleng360/article/details/45192357?locationnum=6)

[Springboot项目 freemarker 引入shiro 标签](https://my.oschina.net/jeakiry/blog/1814811)

模板加载器：

[freemarker模板加载TemplateLoader常见方式](https://www.cnblogs.com/chenfeng1122/p/6884576.html)

[FreeMarker-TemplateLoader](https://www.cnblogs.com/cosyman/p/freemarker-templateloader.html)

补充：

[SpringMVC中Freemarker获取项目根目录](https://www.cnblogs.com/newlangwen/p/9269755.html)

[SpringMVC中Freemarker获取项目根目录](https://blog.csdn.net/whatlookingfor/article/details/51538995)

[SpringMVC与Freemarker集成，配置项目全局的绝对路径](https://blog.csdn.net/pyzheng/article/details/84616379)

实例：

```java
package com.lymatrix.jdcgz.web;

import java.io.IOException;

import javax.servlet.ServletContext;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.web.servlet.ViewResolver;
import org.springframework.web.servlet.config.annotation.DefaultServletHandlerConfigurer;
import org.springframework.web.servlet.config.annotation.EnableWebMvc;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurerAdapter;
import org.springframework.web.servlet.view.InternalResourceViewResolver;
import org.springframework.web.servlet.view.freemarker.FreeMarkerConfigurer;
import org.springframework.web.servlet.view.freemarker.FreeMarkerViewResolver;

import freemarker.cache.WebappTemplateLoader;
import freemarker.template.TemplateException;

@Configuration
@EnableWebMvc
@ComponentScan("com.lymatrix.jdcgz.web")
public class WebConfig extends WebMvcConfigurerAdapter {

    // @Bean
    // public ViewResolver viewResolver() {
    //     InternalResourceViewResolver resolver = new InternalResourceViewResolver();
    //     resolver.setPrefix("/WEB-INF/views/");
    //     resolver.setSuffix(".jsp");
    //     return resolver;
    // }

    /*-----------整合FreeMarker------------*/
    @Autowired
    private ServletContext servletContext;

    @Bean
    public ViewResolver viewResolver() {
        FreeMarkerViewResolver viewResolver = new FreeMarkerViewResolver();
        //viewResolver.setPrefix("/WEB-INF/views/");
        viewResolver.setPrefix("");
        viewResolver.setSuffix(".html");
        viewResolver.setContentType("text/html;charset=UTF-8");
        return viewResolver;
    }

    @Bean
    public FreeMarkerConfigurer freeMarkerConfigurer() throws IOException, TemplateException {
        FreeMarkerConfigurer freeMarkerConfigurer = new FreeMarkerConfigurer();
        //freeMarkerConfigurer.setTemplateLoaderPaths("/WEB-INF/views/");
        freemarker.template.Configuration configuration = freeMarkerConfigurer.createConfiguration();
        configuration.setDefaultEncoding("UTF-8");
        configuration.setDateTimeFormat("yyyy-MM-dd HH:mm:ss");

        //创建一个模板加载器，它将使用指定的servlet上下文来加载资源。指定基本路径，该路径相对于上下文根进行解释
        configuration.setTemplateLoader(new WebappTemplateLoader(servletContext,"/WEB-INF/views/"));
        freeMarkerConfigurer.setConfiguration(configuration);
        return freeMarkerConfigurer;
    }

    @Override
    public void configureDefaultServletHandling(DefaultServletHandlerConfigurer configurer) {
        configurer.enable();
    }
}
```
