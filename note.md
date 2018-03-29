Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

Day 4 -编写Model

Day 5-编写Web框架

Day 6-编写配置文件

Day 7-编写Mvc

<u>Day 8-构建前端</u>

Day 9-编写API

Day 10-用户注册和登录

Day 11-编写日志创建页

Day 12-编写日志列表页

Day 13-提升开发效率

Day 14-完成Web-App

Day 15-部署Web App

Day 16-编写移动App



### 今天要做什么？

前面跑通了一个最简单的MVC，但是页面效果肯定不会让人满意，今天就来设计美观简洁的页面。

### 配置思路
1、下载uikit这个强大的CSS框架并添加一些字体模板到www/static目录下，并按照类别归类:

2、利用uikit这个CSS框架来完父模板\__base__\.html的编写:

3、继承\__base__\.html模板编写首页页面blogs.html:

4、更新handlers.py中的首页URL处理函数：

5、Blog的创建日期显示问题，需在初始化jinja2时设置:



### 参考

[uikit首页](https://getuikit.com/)

### 遇到的问题!!!

1、uikit框架模板只包含了css、js两个文件,需要自己添加fonts字体文件，及img图片文件，修改css和js中的部分自定义。

2、要理解\__base__\.html模板思想

3、关于Blog创建日期问题，在前面初始化app.py中已经配置好了datetime_filter().