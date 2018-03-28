Day 1-搭建开发环境

Day 2-编写Web App骨架

Day 3-编写ORM

Day 4 -编写Model

Day 5-编写Web框架

<u>Day 6-编写配置文件</u>

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

有了Web框架和ORM框架，我们就可以开始装配App了。

通常，一个Web App在运行时都需要读取配置文件，比如数据库的用户名、口令等，在不同的环境中运行时，Web App可以通过读取不同的配置文件来获得正确的配置。



### 配置思路
1、编写本地配置文件config_default.py
2、编写部署环境配置文件config_override.py   #覆盖部分本地配置
3、编写统一获取配置文件config.py



### 参考




### 遇到的问题!!!

1、config_default.py文件中db中user和password与前面初始化数据库SQL脚本中不一致，因统一修改为www-data.