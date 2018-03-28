Day 1-搭建开发环境

Day 2-编写Web App骨架

<u>Day 3-编写ORM</u>

Day 4 -编写Model

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

进一步理解面向对象的思想，认识ORM，并且编写适合自己的ORM.



### 编写ORM的思路

#### 1、创建连接池

def create_pool(loop,**kw):

​	pass

#### 2、编写select()函数和execute()函数

def select(sql,args,size=None):

​	pass

def  execute(sql,args,autocommit=True):

​	pass

#### 3、定义Model

class ModelMetaclass(type):

​	pass

class Model(dict,metaclass=ModelMetaclass):

​	pass

#### 定义及Field和各种Field子类

class Field(object):

​	pass

映射varchar的StringField

class StringField(Field):

​	pass

class BooleanField(Field):

​	pass

#### 其他

### 测试ORM

```bash
#do_orm.py为测试orm是否可行的脚本
import time, uuid
from orm import Model, StringField, BooleanField, FloatField, TextField
import orm,asyncio

def next_id():
    return '%015d%s000' % (int(time.time() * 1000), uuid.uuid4().hex)

#通过orm导入的表父类和列类创建表对象
class User(Model):
    __table__ = 'users'

    id = StringField(primary_key=True, default=next_id, ddl='varchar(50)')
    email = StringField(ddl='varchar(50)')
    passwd = StringField(ddl='varchar(50)')
    admin = BooleanField()
    name = StringField(ddl='varchar(50)')
    image = StringField(ddl='varchar(500)')
    created_at = FloatField(default=time.time)

loop = asyncio.get_event_loop()
    
#测试数据库
@asyncio.coroutine
def test():
    #连接到数据库利用下一节的SQL脚本初始化数据库
    yield from orm.create_pool(loop=loop,user='www-data', password='www-data', db='awesome')
    
    #向数据库中添加信息
    u = User(name='Test', email='test@example.com', passwd='1234567890', image='about:blank')

    yield from u.save()
    
loop.run_until_complete(test())
```

### 遇到的问题!!!

元类、基类、数据库相关知识欠缺.需要加强对数据库工作流程的理解.