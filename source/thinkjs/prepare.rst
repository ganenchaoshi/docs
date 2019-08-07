开发准备
------------

定位功能

前端
=============

- API地址:
    /{moduleName}/{controllerName}/{acitonName}
- method:
    get/post/put/delete
- 参数:
    - query:
        controller中通过this.get()得到
        - action: 必传参数，与method值保持一致
        - 其他query参数
    - body:
        controller中通过this.post()得到
    - file:
        controller中通过this.file()得到文件上传参数

- Headers:
    - Content-Type:
        - application/x-www-form-urlencode
        - application/form-data
        - multipart/form-data
        - application/json
    - Authorization:
        - 即token，需要登录时必须带上

- Response:
    - 返回值::
    
        // 详情
        {"errno":1006,"errmsg":"","data":{}}
        // 列表 
        {"errno":1006,"errmsg":"","data":{"count":10,"totalPages":1,"pageSize":10,"currentPage":1,"data":[]}
        

后端
============

- 确定功能模块
    module、controller
- 确定接口名称
    xxxAction
- logic
    参数校验：
    - xxxAction方法实现
        - method
        - rules
- controller
    接口实现：
        - xxxAction 方法实现
        
- API地址:
    /{module}/{controller}/xxx
