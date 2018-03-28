Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

<u>Day 4 -编写Model</u>

Day 5-编写Web框架

Day 6-编写配置文件

Day 7-编写Mvc

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

上一节我们编写好了自己的ORM，现在就是开始使用了，可参考sqlalchemy的编写思路。



### 编写Model的思路

```bash
1、使用SQL脚本(schema.sql)初始化数据库
> mysql -u root -p
Enter password:******
mysql> source F:\hello world\schema.sql #source file
Query OK, 3 rows affected (0.28 sec)

Query OK, 1 row affected (0.00 sec)

Database changed
Query OK, 0 rows affected (0.00 sec)

Query OK, 0 rows affected (0.28 sec)

Query OK, 0 rows affected (0.22 sec)

Query OK, 0 rows affected (0.18 sec)
mysql> 此处应该有掌声！！！！

2、编写python语言model表（model.py).

3、运行数据库写入代码(testmysql.py)测试数据库，在Navicat中观察数据库变化.
```


### 参考

#### mysql初始化脚本

```bash
-- schema.sql

drop database if exists awesome;

create database awesome;

use awesome;

grant select, insert, update, delete on awesome.* to 'www-data'@'localhost' identified by 'www-data';

create table users (
    `id` varchar(50) not null,
    `email` varchar(50) not null,
    `passwd` varchar(50) not null,
    `admin` bool not null,
    `name` varchar(50) not null,
    `image` varchar(500) not null,
    `created_at` real not null,
    unique key `idx_email` (`email`),
    key `idx_created_at` (`created_at`),
    primary key (`id`)
) engine=innodb default charset=utf8;

create table blogs (
    `id` varchar(50) not null,
    `user_id` varchar(50) not null,
    `user_name` varchar(50) not null,
    `user_image` varchar(500) not null,
    `name` varchar(50) not null,
    `summary` varchar(200) not null,
    `content` mediumtext not null,
    `created_at` real not null,
    key `idx_created_at` (`created_at`),
    primary key (`id`)
) engine=innodb default charset=utf8;

create table comments (
    `id` varchar(50) not null,
    `blog_id` varchar(50) not null,
    `user_id` varchar(50) not null,
    `user_name` varchar(50) not null,
    `user_image` varchar(500) not null,
    `content` mediumtext not null,
    `created_at` real not null,
    key `idx_created_at` (`created_at`),
    primary key (`id`)
) engine=innodb default charset=utf8;
```

#### 测试数据库代码

```bash
#testmysql.py
import orm
from models import User, Blog, Comment
import asyncio

loop = asyncio.get_event_loop()

@asyncio.coroutine
def test():
    #注意修改db,user,password可以填写root的
    yield from orm.create_pool(loop=loop,user='www-data', password='www-data', db='awesome')

    u = User(name='Test', email='test@example.com', passwd='1234567890', image='about:blank')

    yield from u.save()
    
loop.run_until_complete(test())
```



### 遇到的问题!!!

1、在使用测试脚本时发现对于已经写入的信息再次写入会报错.

'pymysql.err.IntegrityError: (1062, "Duplicate entry 'test@example.com' for key 'idx_email'")'

2、数据也存在root用户和数据库的用户.