Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

Day 4 -编写Model

Day 5-编写Web框架

Day 6-编写配置文件

Day 7-编写Mvc

Day 8-构建前端

<u>Day 9-编写API</u>

Day 10-用户注册和登录

Day 11-编写日志创建页

Day 12-编写日志列表页

Day 13-提升开发效率

Day 14-完成Web-App

Day 15-部署Web App

Day 16-编写移动App



### 今天要做什么？

编写API.不为什么要编写API？

由于API把Web App的功能全部封装了，所以通过API操作数据,可以极大地把前端和后端的代码隔离，

使得后端代码易于测试，前端代码编写简单。

### 具体思路
1、一个API也是一个URL处理函数.

2、通过一个@api把函数变成JSON格式的REST  API.

3、获取注册用户用一个API实现，返回一个dict,然后通过response这个middleware把结果序列化为JSON并返回。

4、添加APIError对Error进行处理。Error是指API调用时发生了逻辑错误(比如用户不存在)，其他Error视为Bug,返回错误代码internalerror.

### 参考

### 实现步骤

1、在handlers.py文件中添加@get('api/users')修饰的def api_users()：函数.

2、在执行1后发现omr.py文件被修改了，所以要替换orm.py文件.



### 遇到的问题!!!

1、按照上面的实现步骤1执行后，运行app.py在浏览器访问http://127.0.0.1:9000/api/users时出现500 Internal Server Error错误

```bash
ERROR:aiohttp.server:Error handling request
Traceback (most recent call last):
  File "E:\Anaconda\setup\lib\site-packages\aiohttp\web_protocol.py", line 381, in start
    resp = await self._request_handler(request)
  File "E:\Anaconda\setup\lib\site-packages\aiohttp\web_app.py", line 310, in _handle
    resp = await handler(request)
  File "E:\Anaconda\setup\lib\site-packages\aiohttp\web_middlewares.py", line 88, in impl
    return await handler(request)
  File "app.py", line 46, in logger
    return (await handler(request))
  File "app.py", line 64, in response
    r = await handler(request)
  File "E:\Anaconda\setup\lib\site-packages\aiohttp\web_urldispatcher.py", line 136, in handler_wrapper
    result = await result
  File "F:\python\liaoxuefeng\app\www\coroweb.py", line 138, in __call__
    r = await self._func(**kw)
  File "E:\Anaconda\setup\lib\asyncio\coroutines.py", line 213, in coro
    res = yield from res
  File "F:\python\liaoxuefeng\app\www\handlers.py", line 29, in api_get_users
    users = yield from User.findAll(orderBy='created_at desc')
TypeError: cannot 'yield from' a coroutine object in a non-coroutine generator
```

发现app.py中未导入config ,导入configs后发现依然不行，在对比了廖老师的源码后发现是orm.py文件被修改了.先替换orm.py跑起来再说，框架问题现在理解功力还是欠缺。

2、关于APIError，前面已经添加过了apis.py文件,import也执行过.