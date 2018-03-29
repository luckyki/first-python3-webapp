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

<u>Day 11-编写日志创建页</u>

Day 12-编写日志列表页

Day 13-提升开发效率

Day 14-完成Web-App

Day 15-部署Web App

Day 16-编写移动App



### 今天要做什么？

编写日志创建页

由于API把Web App的功能全部封装了，所以通过API操作数据,可以极大地把前端和后端的代码隔离，

使得后端代码易于测试，前端代码编写简单。

### 具体思路


### 参考

初始化Vue；

通过Vue关联Model和View

```bash
<!-- input的value和Model的name关联起来了 -->
<input v-model="name" class="uk-width-1-1">
```

Form表单通过<form v-on="submit:submit">把提交表单的事件关联到submit方法。



### 实现步骤

1、选择[Vue](https://vuejs.org/)这个简单的MVVM框架来实现创建Blog的页面manage_blog_edit.html.



### 具体实现

1、在handlers.py中编写如下API和函数(直接替换handlers.py文件)

api_create_blog()

api_get_blog()

manage_create_blog()

get_blog(id)

text2html(text)

get_page_index(page_str)

check_admin(request)

2、在apis.py中添加分页类class Page(object):

3、在app.py中添加

auth_factory(app,handler):(直接替换app.py文件)

4、在templates下添加manage_blog_edit.html

5、修改权限问题.去掉两处not.

### 遇到的问题!!!

1、MVVM模型理解。

2、理解MVVM的Model和View的双向绑定。

3、登录localhost:9000/namager/blogs/create会返回localhost:9000/signin页。

解决方法：

A、修改app.py中  的auth_factory(app,handler):中的if request.path.startswitch():去掉其中的not。

B、修改handlers.py中的check_admin(request):中if判断句，去掉not。