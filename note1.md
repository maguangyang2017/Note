 ***Web入门开发***

     Internet上供外部开发的Web资源分为：（静态Web资源和动态Web资源）
     静态和动态并不是指网页的动画，而是指网页内容是否自动更新

     静态Web资源开发技术：Html
     动态Web资源开发技术：JSP/Servlet、ASP、PHP等

     通过web.xml文件可以将Web应用中的：

      某个web资源配置为网站首页
      将servlet程序映射到某个url地址上
    但凡涉及到对web资源进行配置，都需要通过web.xml文件

***HTTP协议***

  HTTP是hypertext transfer protocol（超文本传输协议）的简写，它是TCP/IP协议的一个应用层协议，用于定义WEB浏览器与WEB服务器之间交换数据的过程

  HTTP请求

    请求行
    消息头
    （空行）
    请求实体内容

  请求方式有：POST、GET、HEAD、OPTIONS、DELETE、TRACE、PUT

  常用的有：post、get



  HTTP响应


    状态行
    相应消息
    （空行）
    相应实体

  HttpServletRequest对象代表客户端的请求，当客户端通过HTTP协议访问服务器时，HTTP请求头中的所有信息都封装在这个对象中，开发人员通过这个对象的方法，可以获得客户这些信息

  request常用方法

    getRequestURL方法返回客户端发出请求时的完整URL。
    getRequestURI方法返回请求行中的资源名部分。
    getQueryString 方法返回请求行中的参数部分。
    getPathInfo方法返回请求URL中的额外路径信息。额外路径信息是请求URL中的位于Servlet的路径之后和查询参数之前的内容，它以“/”开头。
    getRemoteAddr方法返回发出请求的客户机的IP地址
    getRemoteHost方法返回发出请求的客户机的完整主机名
    getRemotePort方法返回客户机所使用的网络端口号
    getLocalAddr方法返回WEB服务器的IP地址。
    getLocalName方法返回WEB服务器的主机名

  request常见应用

    获取浏览器类型
    防盗链
    各种表单输入项的获取（text、password、radio、checkbox、file、select、textarea、 hidden、）

***Servlet的部署***


应用程序的开发过程:
``` html
第一步：实现Servlet接口
第二步：要在WEB-INF目录找web.xml文件
  <servlet>
    <servlet-name>index</servlet-name>
    <servlet-class>com.test.IndexServlet</servlet-class>
    <init-param>
        <param-name>classdebuginfo</param-name>
        <param-value>true</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
  </servlet>
  <servlet-mapping>
    <servlet-name>index</servlet-name>
    <url-pattern>/gaoxin</url-pattern>
    <url-pattern>/songjun</url-pattern>
  </servlet-mapping>
第三步：部署项目，相当于放到了webapps目录下面

  Web服务器调用Servlet的过程

    Servlet程序是由WEB服务器调用，web服务器收到客户端的Servlet访问请求后：
    Web服务器首先检查是否已经装载并创建了该Servlet的实例对象。如果是，则直接执行第④步，否则，执行第②步。
    装载并创建该Servlet的一个实例对象。
    调用Servlet实例对象的init()方法。
    创建一个用于封装HTTP请求消息的HttpServletRequest对象和一个代表HTTP响应消息的HttpServletResponse对象，然后调用Servlet的service()方法并将请求和响应对象作为参数传递进去。
    WEB应用程序被停止或重新启动之前，Servlet引擎将卸载Servlet，并在卸载之前调用Servlet的destroy()方法。
