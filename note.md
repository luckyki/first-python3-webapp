Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

Day 4 -编写Model

Day 5-编写Web框架

Day 6-编写配置文件

<u>Day 7-编写Mvc</u>

Day 8-构建前端

Day 9-编写API

Day 10-用户注册和登录

Day 11-编写日志创建页

Day 12-编写日志列表页

Day 13-提升开发效率

Day 14-完成Web-App

Day 15-部署Web App

Day 16-编写移动App



### 今天要做什么？

现在，ORM框架、Web框架和配置都已就绪，我们可以开始编写一个最简单的MVC，把它们全部启动起来。

### 配置思路
1、在handlers.py中编写首页URLD的函数

2、在模板的根目录templates下创建test.html

3、运行app.py查看效果

### 参考



### 遇到的问题!!!

1、命令行下运行app.py出现如下错误，注意看File "app.py", line 113, in init可知是数据库名字和密码与SQL脚本中初始化的不一样，改成www-data即可，或者直接改成root权限及密码。
```bash
Traceback (most recent call last):
  File "app.py", line 125, in <module>
    loop.run_until_complete(init(loop))
  File "E:\Anaconda\setup\lib\asyncio\base_events.py", line 467, in run_until_complete
    return future.result()
  File "app.py", line 113, in init
    await orm.create_pool(loop=loop, host='127.0.0.1', port=3306, user='www', password='www', db='awesome')
  File "F:\python\liaoxuefeng\app\www\orm.py", line 24, in create_pool
    loop=loop
  File "E:\Anaconda\setup\lib\site-packages\aiomysql\utils.py", line 75, in __await__
    resp = yield from self._coro
  File "E:\Anaconda\setup\lib\site-packages\aiomysql\pool.py", line 30, in _create_pool
    yield from pool._fill_free_pool(False)
  File "E:\Anaconda\setup\lib\site-packages\aiomysql\pool.py", line 173, in _fill_free_pool
    **self._conn_kwargs)
  File "E:\Anaconda\setup\lib\site-packages\aiomysql\utils.py", line 70, in __iter__
    resp = yield from self._coro
  File "E:\Anaconda\setup\lib\site-packages\aiomysql\connection.py", line 78, in _connect
    yield from conn._connect()
  File "E:\Anaconda\setup\lib\site-packages\aiomysql\connection.py", line 496, in _connect
    self._host) from e
pymysql.err.OperationalError: (2003, "Can't connect to MySQL server on '127.0.0.1'")

```

