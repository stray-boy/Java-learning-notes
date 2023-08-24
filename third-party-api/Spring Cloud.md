# Spring Cloud 对应版本信息
https://github.com/alibaba/spring-cloud-alibaba/wiki/%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E
列举部分
Spring Cloud Alibaba Version	Spring Cloud Version	Spring Boot Version
2022.0.0.0*                     Spring Cloud 2022.0.0      3.0.2
2022.0.0.0-RC2                  Spring Cloud 2022.0.0      3.0.2
2022.0.0.0-RC1                  Spring Cloud 2022.0.0      3.0.0
2021.0.5.0*                     Spring Cloud 2021.0.5      2.6.13
2021.0.4.0                      Spring Cloud 2021.0.4      2.6.11
2021.0.1.0                      Spring Cloud 2021.0.1      2.6.3
2021.1                          Spring Cloud 2020.0.1      2.4.2
对于构建的新项目多数使用的jdk8以及适配的代码，对于JDK的版本没有做特别的更新，本次使用的版本信息如下
<properties>
    <spring.cloud.version>Hoxton.SR12</spring.cloud.version>
    <spring.cloud.alibaba.version>2.2.9.RELEASE</spring.cloud.alibaba.version>
    <spring.boot.version>2.3.12.RELEASE</spring.boot.version>
    <java.version>8</java.version>
</properties>

对应的nacos版本信息为（对于springcloud的开发需要格外注意版本信息的不同导致各种问题的产生）本次使用版本
https://github.com/alibaba/nacos/releases/download/2.1.1/nacos-server-2.1.1.zip

各项目依赖导致不能够自动导入包，所以需要在启动类上进行加载
@MapperScan("com.maywide.cmms.*.mapper")
@ComponentScan("com.maywide.cmms.*.service")
@ServletComponentScan("com.maywide")
@ImportResource({"classpath:config/xml/spring-context.xml", "classpath:config/xml/spring-quartz.xml"})




