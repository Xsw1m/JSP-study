# JSP-study
Velocity模块 --- JSP 
#### 一、JSP el表达式
```
1、语法结构
     ${expression}
2、[ ]与.运算符
     EL 提供“.“和“[ ]“两种运算符来存取数据。
     当要存取的属性名称中包含一些特殊字符，如.或?等并非字母或数字的符号，就一定要使用“[ ]“。例如：
         ${user.My-Name}应当改为${user["My-Name"] }
     如果要动态取值时，就可以用“[ ]“来做，而“.“无法做到动态取值。例如：
         ${sessionScope.user[data]}中data 是一个变量
3、变量
     EL存取变量数据的方法很简单，例如：${username}。它的意思是取出某一范围中名称为username的变量。
     因为我们并没有指定哪一个范围的username，所以它会依序从Page < Request < Session < Application范围查找。
     假如途中找到username，就直接回传，不再继续找下去，但是假如全部的范围都没有找到时，就回传null。
     属性范围在EL中的名称
         Page          PageScope
         Request          RequestScope
         Session          SessionScope
         Application      ApplicationScope
```
#### 二、javaWeb 四种范围
```
1.简单说 page指当前页面。在一个jsp页面里有效 
2.request 指从http请求到服务器处理结束，返回响应的整个过程。
在这个过程中使用forward方式跳转多个jsp。在这些页面里你都可以使用这个变量。 
其实有点像HttpServletRequest，在所相关的网页都可以获取到请求网页的相关信息一样
3.Session 有效范围当前会话，从浏览器打开到浏览器关闭这个过程。 每个用户都有唯一的一个
4.application它的有效范围是整个应用。 作用域里的变量，它们的存活时间是最长的，如果不进行手工删除，它们就一直可以使用 
```
