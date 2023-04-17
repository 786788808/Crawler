## WebScrape

### 1.HTTP 基础：
HTTP是超文本传输协议，其定义了客户端与服务器端之间文本传输的规范。HTTP默认使用80端口，这个端口指的是服务端的端口，而客户端使用的端口是动态分配的。当我们没有指定端口访问时，浏览器会默认帮我们添加80端口。我们也可以自己指定访问端口如：http://www.baidu.com:80。 需要注意的是，现在大多数访问都使用了HTTPS协议，而HTTPS的默认端口为443，如果使用80端口访问HTTPS协议的服务器可能会被拒绝。  
HTTP协议定义Web客户端如何从Web服务器请求Web页面，以及服务器如何把Web页面传送给客户端。HTTP协议采用了请求/响应模型。客户端向服务器发送一个请求报文，请求报文包含请求的方法、URL、协议版本、请求头部和请求数据。服务器以一个状态行作为响应，响应的内容包括协议的版本、成功或者错误代码、服务器信息、响应头部和响应数据。

### 2.HTTP 请求/响应的步骤：
客户端连接到Web服务器->发送Http请求->服务器接受请求并返回HTTP响应->释放连接TCP连接->客户端浏览器解析HTML内容

### 3.HTTP的请求方法
HTTP/1.1 协议中定义了八种方法，来表明 Request-URL 指定的资源不同的操作方式  
HTTP1.0 定义了三种请求方法：GET, POST 和 HEAD 方法  
HTTP1.1 新增了五种请求方法：OPTIONS, PUT, DELETE, TRACE 和 CONNECT 方法  
FYIhttps://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT

[HTTP MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECTA)

### 4.
Request Line:请求行  
Header:请求头  
(空行)  
Request Body:请求体  
响应行  
响应消息头  
响应消息体  

### 状态码：
200 - 请求成功  

4xx:表示客户端请求有错误  
400: 表示客户端请求不符合接口要求，比如格式完全错误      
401: 表示客户端需要先认证才能发送此请求  
403: 表示客户端没权限要求服务器处理这样的请求，比如普通用户请求删除别人的账号  
404: 客户端请求的URL不存在    
