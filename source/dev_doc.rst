开发参考文档
---------------

API 联调
=========

    在前台界面通过快速信息收集，可以迅速复现错误，从而快速修复。

    .. note::
        通过鼠标3击以下几种信息的高亮部分，即可快速选中信息进行复制(ctrl + c)

错误收集
^^^^^^^^
    F12 >> Network >> Response::

        {"errno":1006,"errmsg":"无效的参数","data":{"message":"任务结束时间不能大于项目结束时间"}}

    .. note::
        数据正常返回，但不正确，可截图圈出问题部分：
        F12 >> Network >> Preview

API参数
^^^^^^^^
    F12 >> Network >> Headers

    #. URL
        >> Genernal >> Request URL
        
        .. code:: python
        
            Request URL: https://service.supergen-edu.com/admin/projectTask/update?action=put&id=4
    #. token
        >> Request Headers >> Authorization

        .. code::

            Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwibmFtZSI6ImFkbWluIiwiaWF0IjoxNTU3NTM5OTEzLCJleHAiOjE1NjAxMzE5MTMsImF1ZCI6IlVzZXIiLCJpc3MiOiJOYXJ3aGFsZSBJbmMuIiwic3ViIjoiQWNjZXNzVG9rZW4iLCJqdGkiOiJhZWI2NDZkNTI4OTQ0M2YyYjA4ODM3NmQ3ZDFlOTM1ZCJ9.RZdx7iO59Sv3PQLY2G14r9WE7rIPBUnHsLKhb1PIZsY

    #. 参数
        >> Request Payload >> view source

        .. code::

            {"name":"疼羊肉汤","intro":"撒打算","requirement":"递四方速递","startTime":"2019-04-04 12:00:00","endTime":"2019-04-06 12:00:00","projectId":"6"}

