# Tomcat简介
```
Tomcat是一个开源的Java Servlet容器，也可以作为独立的Web服务器使用。它由Apache软件基金会开发和维护，并且完全符合Java Servlet、JavaServer Pages (JSP)和WebSocket规范。以下是对Tomcat的简介：
1. Java Servlet容器：作为Servlet容器，Tomcat提供了执行Servlet代码并处理HTTP请求和响应的环境。它负责管理Servlet生命周期、线程池、请求分发以及与其他组件（如数据库）进行交互。
2. Web服务器功能：除了支持Servlet技术外，Tomcat还具备一些传统Web服务器的功能。它能够处理静态资源（如HTML文件）、支持HTTPS协议、实现虚拟主机配置等。
3. 轻量级和易于部署：相比于其他大型应用服务器，Tomcat被设计为轻量级且易于部署。您只需下载适合您操作系统类型的二进制文件并解压即可开始使用。
4. 可扩展性：通过集成各种插件和扩展包（例如连接池、安全模块），Tomcat可以根据需要进行功能上的扩展，并满足不同项目或应用程序的需求。
5. 易用性与广泛采纳率：由于其简单易用性以及在企业中广泛采纳，Tomcat成为最受欢迎的Java Servlet容器之一。它具有丰富的文档资源、活跃的开发者社区和大量可用的第三方工具和库。
6. 可移植性：Tomcat在多个平台上都可以运行，包括Windows、Linux和Mac OS等。这使得开发人员能够在不同环境中保持一致，并轻松迁移其应用程序。
总而言之，Tomcat是一个功能强大且易于使用的Java Servlet容器，适合于开发和部署各种规模的Web应用程序。无论是小型网站还是企业级应用系统，Tomcat都提供了稳定可靠的基础架构来支持Java Web开发。
```

# HTTP请求常见请求码
```
## 1XX 信息100 
Continue : 表明到目前为止都很正常，客户端可以继续发送请求或者忽略这个响应。
## 2XX 成功
200 OK  
204 No Content : 请求已经成功处理，但是返回的响应报文不包含实体的主体部分。一般在只需要从客户端往服务器发送信息，而不需要返回数据时使用。
206 Partial Content : 表示客户端进行了范围请求，响应报文包含由 Content-Range 指定范围的实体内容。
## 3XX 重定向
301 Moved Permanently : 永久性重定向
302 Found : 临时性重定向
303 See Other : 和 302 有着相同的功能，但是 303 明确要求客户端应该采用 GET 方法获取资源。注: 虽然 HTTP 协议规定 301、302 状态下重定向时不允许把 POST 方法改成 GET 方法，但是大多数浏览器都会在 301、302 和 303 状态下的重定向把 POST 方法改成 GET 方法。
304 Not Modified : 如果请求报文首部包含一些条件，例如: If-Match，If-Modified-Since，If-None-Match，If-Range，If-Unmodified-Since，如果不满足条件，则服务器会返回 304 状态码。
307 Temporary Redirect : 临时重定向，与 302 的含义类似，但是 307 要求浏览器不会把重定向请求的 POST 方法改成 GET 方法。
## 4XX 客户端错误
400 Bad Request : 请求报文中存在语法错误。
401 Unauthorized : 该状态码表示发送的请求需要有认证信息(BASIC 认证、DIGEST 认证)。如果之前已进行过一次请求，则表示用户认证失败。
403 Forbidden : 请求被拒绝。
404 Not Found
## 5XX 服务器错误
500 Internal Server Error : 服务器正在执行请求时发生错误。
503 Service Unavailable : 服务器暂时处于超负载或正在进行停机维护，现在无法处理请求。
```
# 参考文档
```
https://pdai.tech/md/framework/tomcat/tomcat-overview.html
```












