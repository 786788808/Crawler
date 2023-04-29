## WebScrape

HTML + CSS + JavaScript

体验版：
```<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Hush Testing</title>
</head>
<body>
 
<h1>header1</h1>
 
<p>part1</p>
 
</body>
</html>
```
rename to demo.html, and then 拖到浏览器，这就是一个html了  

### 1.HTTP 基础：
HTTP是超文本传输协议，其定义了客户端与服务器端之间文本传输的规范。HTTP默认使用80端口，这个端口指的是服务端的端口，而客户端使用的端口是动态分配的。当我们没有指定端口访问时，浏览器会默认帮我们添加80端口。我们也可以自己指定访问端口如：http://www.baidu.com:80。 需要注意的是，现在大多数访问都使用了HTTPS协议，而HTTPS的默认端口为443，如果使用80端口访问HTTPS协议的服务器可能会被拒绝。  
HTTP协议定义Web客户端如何从Web服务器请求Web页面，以及服务器如何把Web页面传送给客户端。HTTP协议采用了请求/响应模型。客户端向服务器发送一个请求报文，请求报文包含请求的方法、URL、协议版本、请求头部和请求数据。服务器以一个状态行作为响应，响应的内容包括协议的版本、成功或者错误代码、服务器信息、响应头部和响应数据。

HTTP 协议最大的特点是 通讯双方 分为 客户端 和 服务端 。
由于 目前 HTTP是基于 TCP 协议的， 所以要进行通讯，客户端 必须先 和服务端 创建 TCP 连接。
而且 HTTP 双方的信息交互，必须是这样一种方式：
客户端 先发送 http请求（request）给 服务端
然后服务端 发送 http响应（response）给 客户端
特别注意：HTTP协议中，服务端不能主动先发送信息给 客户端。
而且在1.1 以前的版本， 服务端 返回响应给客户端后，连接就会 断开 ，下一次双方要进行信息交流，必须重复上面的过程，重新建立连接，客户端发送请求，服务返回响应。
到了 1.1 版本， 建立连接后，这个连接可以保持一段时间（keep alive）， 这段时间，双方可以多次进行 请求和响应， 无需重新建立连接。

### 2.HTTP 请求/响应的步骤：
客户端连接到Web服务器->发送Http请求->服务器接受请求并返回HTTP响应->释放连接TCP连接->客户端浏览器解析HTML内容

- 客户端连接到Web服务器
一个HTTP客户端，通常是浏览器，与Web服务器的HTTP端口（默认为80）建立一个TCP套接字连接。例如，http://www.baidu.com

- 发送HTTP请求
通过TCP套接字，客户端向Web服务器发送一个文本的请求报文，一个请求报文由请求行、请求头部、空行和请求数据4部分组成。

- 服务器接受请求并返回HTTP响应
Web服务器解析请求，定位请求资源。服务器将资源复本写到TCP套接字，由客户端读取。一个响应由状态行、响应头部、空行和响应数据4部分组成。

- 释放连接TCP连接
若connection 模式为close，则服务器主动关闭TCP连接，客户端被动关闭连接，释放TCP连接;若connection 模式为keepalive，则该连接会保持一段时间，在该时间内可以继续接收请求;

- 客户端浏览器解析HTML内容
客户端浏览器首先解析状态行，查看表明请求是否成功的状态代码。然后解析每一个响应头，响应头告知以下为若干字节的HTML文档和文档的字符集。客户端浏览器读取响应数据HTML，根据HTML的语法对其进行格式化，并在浏览器窗口中显示。

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

###
r = requests.post(url=fileURL, data=payload, headers=headers, proxies=proxies)  

### 
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
