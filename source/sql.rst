基本查询
=========

详情
^^^^^^^^^^^^^^^^^^

    .. code:: mysql

        # 查询id为1的用户信息
        select * from user where id = 1;

    .. note::
        - 要得到某一行数据，**查询条件** (where子句)必须 **唯一** 确定，否则得到的是多条数据

列表
^^^^^^^^^^^^^^^^^^
    - 不需分页
        .. code:: mysql

            # 不需分页 - 轮播图列表
            select * from banner where is_delete = 0;

    - 需要分页 - 用户列表:
        .. code:: mysql

            select * from user where is_delete = 0 limit 0, 5;

    - 筛选 - 按限定条件查询
        .. code:: mysql
            
            # 状态为报名中的项目
            select * from project where is_delete = 0 and status = 1 limit 0, 5

            # 腾讯发布的项目: 假定腾讯的机构id为1(即company_id = 1):
            select * from project where is_delete = 0 and is_published = 1 and company_id = 1 limit 0, 5;

    .. note::

        - 分页语法: limit offset, pageSize, 其中offset = (page - 1) * pageSize
        - is_delete: 软删除，值为0为未删除，非0时表示已删除

新增
^^^^^^^

    .. code:: mysql

        # 增加搜索记录
        insert into search(keyword,search_count) values('腾讯', 0);
        
    .. note::

        - 前后两个()括号中分别是字段和字段对应的值


编辑
^^^^^^^
    - 单项更新:
        .. code:: mysql

            # 编辑用户信息: 名字、email
            update user set name = '我是谁', email = 'jack@163.com' where id = 1;

    - 批量更新
        .. code:: mysql

            # 禁用id出现在列表[1,2]中的用户
            update user set status = -1 where id in (1,2);

删除
^^^^^
    - 单项删除
        .. code:: mysql

            # 删除id=1的搜索记录
            delete from search where id = 1;
    - 批量删除
        .. code:: mysql

            # 批量删除: 删除id包含在[1,2]列表中的搜索记录
            delete from search where id in (1, 2);
    
.. warning::

    - 编辑/删除 数据时，要 **特别小心** ，如果是针对单条数据的，一定要 **限制好查询条件** ，以免变成 **批量** 操作


    


