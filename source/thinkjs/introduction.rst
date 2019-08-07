介绍
------------

项目结构
=========

.. code::

    └── server
        ├── ext                  # 引入外部文件
        │   ├── constants        # 常量
        │   │   ├── constants.js
        │   │   └── region.json
        │   └── utils            # 写点工具代码
        │       └── ...
        ├── logs                 # 日志文件
        │   └── ...
        ├── nginx.conf           # 部署相关
        ├── ecosystem.config.js  # 部署相关
        ├── pm2.json             # 部署相关
        ├── node_modules
        │       └── ...
        ├── package.json         # 
        ├── development.js       # development环境入口文件
        ├── production.js        # production环境入口文件
        └── src                  # thinkjs源码目录
            ├── admin            # thinkjs module, 后台API写在这个模块中
            │   ├── config       # 目前主要用于配置API访问是否需要验证token
            │   ├── controller   # 控制器目录，API的实现写在这里
            │   ├── logic        # logic层，API 参数、参数验证，controller中文件、action接口名称与controller中一一对应
            │   └── model        # 模型文件，作用同common >> model
            ├── common           # thinkjs module, 公共接口、配置
            │   ├── bootstrap    # 项目启动时执行的操作
            │   ├── config       # 项目相关配置：数据库、中间件、路由等
            │   ├── extend       # 可对thinkjs进行扩展
            │   ├── middleware   # 可用于自定义中间件
            │   ├── model        # 模型文件，数据库的一些公共方法可写在这里
            │   └── service      # 主要用于抽象controller中用到的一些公共的方法，业务逻辑。
            └── home             # thinkjs module, 前端API写在这个模块中，相关介绍参看admin模块
               ├── config
               ├── controller
               ├── logic
               └── model

.. seealso::
    `thinkjs 官网`_

    .. _`thinkjs 官网`: http://www.thinkjs.org

常量
===========
- 路径：server/ext/constants/constants.js
- 主要常量:
    =============  =========
    MODEL_NAMES     表名
    SETTINGS        设置
    STATUS          状态
    TYPES           类型
    ERRORS          错误码
    =============  =========

