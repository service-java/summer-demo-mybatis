#### JSP基础

* 调试

```
// 使用JDB Logger

// 使用Log4J 框架
将消息记录在不同的文件中，这些消息基于严重程度和重要性来进行分类

// 调试工具
// NetBeans
断点
单步跟踪
观察点

// 使用JDB Debugger

```

* 国际化

```
<%@ page import="java.io.*,java.util.Locale" %>

response.setHeader("Content-Language", "es"); // 设置语言

<%@ page import="java.text.DateFormat,java.util.Date" %> // 时间

<%@ page import="java.text.NumberFormat,java.util.Date" %> // 货币

<%@ page import="java.text.NumberFormat,java.util.Date" %> // 百分比
```

* Cookie与session

```
// 访问量统计

session用于记录1次 // 防止不断刷新
application用于记录所有次数

// 获取session创建时间
Date createTime = new Date(session.getCreationTime());
   
// 获取最后访问页面的时间
Date lastAccessTime = new Date(session.getLastAccessedTime());

  // 检测网页是否由新的访问用户
   if (session.isNew()){
      title = "访问菜鸟教程实例";
      session.setAttribute(userIDKey, userID);
      session.setAttribute(visitCountKey,  visitCount);
   } else {
	   visitCount = (Integer)session.getAttribute(visitCountKey);
	   visitCount += 1;
	   userID = (String)session.getAttribute(userIDKey);
	   session.setAttribute(visitCountKey,  visitCount);
   }
   
   // 可以在web.xml里设置超时
     <session-config>
       <session-timeout>15</session-timeout>
     </session-config>
     
     
     // cookie
     String   str   =   java.net.URLEncoder.encode("中文");            //编码
     String   str   =   java.net.URLDecoder.decode("编码后的字符串");   // 解码
     out.print("参数值: " + URLDecoder.decode(cookie.getValue(), "utf-8") +" <br>");
     
     
     // 删除
     if((cookie.getName( )).compareTo("name") == 0 ){
                 cookie.setMaxAge(0);
     }           
```

* 过滤器
    * [过滤器](http://www.runoob.com/jsp/jsp-writing-filters.html)
```

```

* 其他
    * [状态码](http://www.runoob.com/jsp/jsp-http-status-codes.html)

```
// 时间日期
比较
格式转化

// 生命周期

// 状态码
```