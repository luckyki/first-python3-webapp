Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

Day 4 -编写Model

Day 5-编写Web框架

Day 6-编写配置文件

Day 7-编写Mvc

Day 8-构建前端

Day 9-编写API

<u>Day 10-用户注册和登录</u>

Day 11-编写日志创建页

Day 12-编写日志列表页

Day 13-提升开发效率

Day 14-完成Web-App

Day 15-部署Web App

Day 16-编写移动App



### 今天要做什么？

实现用户注册和登录

由于API把Web App的功能全部封装了，所以通过API操作数据,可以极大地把前端和后端的代码隔离，

使得后端代码易于测试，前端代码编写简单。

### 具体思路


### 参考



### 实现步骤

1、编写用户注册API。

2、接着创建一个注册页面，供用户填写注册表单，然后，提交数据到注册用户的API。

3、编写用户登录API。

4、编写middle，实现处理URL之前，把cookie解析出来，并将登录用户绑定到request对象上。

5、编写登录页面。



### 具体实现

1、在handlers.py中编写用户注册API;

2、在templates中编写注册页面register.html；在handlers.py中添加注册页函数regiser()

3、在handlers.py编写登录API(可以直接替换handlers.py文件)；

4、在app.py中编写auth_factory()这个middle处理cookie

5、在templates中编写用户登录页面signin.html。

6、复制markdown2.py文件

### 遇到的问题!!!

1、API的理解.

2、Session封装cookie和直接cookie验证登录，及cookie防伪造处理.

3、登录middle的理解.

4、执行上面的五个步骤出现

ModuleNotFoundError: No module named 'markdown2'

此时可以复制markdown2.py文件了

