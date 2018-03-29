Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

Day 4 -编写Model

Day 5-编写Web框架

Day 6-编写配置文件

Day 7-编写Mvc

Day 8-构建前端

Day 9-编写API

Day 10-用户注册和登录

Day 11-编写日志创建页

<u>Day 12-编写日志列表页</u>

Day 13-提升开发效率

Day 14-完成Web-App

Day 15-部署Web App

Day 16-编写移动App



### 今天要做什么？

编写日志列表页

由于API把Web App的功能全部封装了，所以通过API操作数据,可以极大地把前端和后端的代码隔离，

使得后端代码易于测试，前端代码编写简单。

### 具体思路

1、在apis.py中定义一个Page类用于存储分页信息

2、在handlers.py中实现api_get_blog()API及manage_blogs()管理页面

3、在templates下添加manage_blogs.html




### 参考





### 实现步骤

1、替换handlers.py文件

2、在templates中添加manage_blogs.html



### 遇到的问题!!!

1、apis.py中的Pages类前面已经存在。
