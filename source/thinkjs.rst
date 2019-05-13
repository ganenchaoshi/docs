常量
--------
- 路径：server/ext/constants/constants.js
- 主要常量:
    =============  =========
    MODEL_NAMES     表名
    SETTINGS        设置
    STATUS          状态
    TYPES           类型
    ERRORS          错误码
    =============  =========

API 编写
--------------


.. code:: shell

    # 在home模块下创建courseCategory控制器
    $ thinkjs controller courseCategory home

.. note::

    上述命令将创建两个文件：
        - logic/courseCategory.js 用于参数校验
        .. code::

            module.exports = class extends think.Logic {
                indexAction() {

                }
            }

        - controller/courseCategory.js 用于编写接口逻辑代码
        .. code::
        
            const Base = require('./base.js');
            // 表名常量
            const MODEL_NAMES = think.CONST.MODEL_NAMES;

            module.exports = class extends Base {
                indexAction() {

                }
            }


列表
^^^^^^
- logic/courseCategory.js

.. code:: javascript

    listAction() {
        this.allowMethods = 'get';
        this.validateParamAction();
        let rules = {
            page: {
                // required为false时，表示该参数为非必传参数
                required: false,
                int: {min: 1}
            },
            pageSize: {
                required: false,
                int: {min: 1}
            }
        };

        const flag = this.validate(rules);
        if (!flag) {
            return this.raise(1006, this.validateErrors);
        }
    }

- controller/courseCategory.js

.. code:: javascript

    async listAction() {
        const {page = 1, pageSize = 2} = this.get();
        const modelCourseCategory = think.getModel(MODEL_NAMES.COURSE_CATEGORY);

        // 不分页的语法
        // let list = await modelCourseCategory.where({is_delete: 0}).select();

        // 分页的语法
        let list = await modelCourseCategory.where({is_delete: 0}).page(page, pageSize).countSelect();

        this.success(list);
    }

详情
^^^^^^^^^^^^^^^^^^
- logic/courseCategory.js

.. code:: javascript

    detailAction() {
        this.allowMethods = 'get';
        this.validateParamAction();
        let rules = {
            id: {
                required: true,
                int: {min: 1},
                // 与访问方法相同时，可省略
                method: 'get'
            }
        };

        const flag = this.validate(rules);
        if (!flag) {
            return this.raise(1006, this.validateErrors);
        }
    }

- controller/courseCategory.js

.. code:: javascript

    async detailAction() {
        const {id} = this.get();
        const modelCourseCategory = think.getModel(MODEL_NAMES.COURSE_CATEGORY);

        let detail = await modelCourseCategory.where({id: id}).find();

        this.success(detail);
    }
        

新增
^^^^^^
- logic/courseCategory.js

.. code:: javascript

    createAction() {
        this.allowMethods = 'post';
        this.validateParamAction();

        // 放在最后面
        let rules = {
            name: {
                required: true,
                string: true,
                length: {
                    min: 1
                }
            },
        };

        const flag = this.validate(rules);
        if (!flag) {
            return this.raise(1006, this.validateErrors);
        }
    }

- controller/courseCategory.js

.. code:: javascript

    async createAction() {
        const {name} = this.post();
        const modelCourseCategory = think.model(MODEL_NAMES.COURSE_CATEGORY);

        const createData = {
            name,
            is_delete: 0,
            // 其他字段
        };

        await modelCourseCategory.add(createData);

        this.success();
    }

编辑
^^^^^^
- logic/courseCategory.js

.. code:: javascript

    updateAction() {
        this.allowMethods = 'put';
        this.validateParamAction();

        // 放在最后面
        let rules = {
            id: {
                required: true,
                int: {
                    min: 1
                },
                method: 'get'
            },
            name: {
                required: true,
                string: true,
                length: {
                    min: 1
                }
            },
        };

        const flag = this.validate(rules);
        if (!flag) {
            return this.raise(1006, this.validateErrors);
        }
    }

- controller/courseCategory.js

.. code:: javascript

    async updateAction() {
        const {id} = this.get();
        const {name} = this.post();
        const modelCourseCategory = think.getModel(MODEL_NAMES.COURSE_CATEGORY);

        const updateData = {
            name: name,
            // 其他需要修改的字段
        };
        await modelCourseCategory.where({id: id}).update(updateData);

        this.success();
    }

删除
^^^^^^
- logic/courseCategory.js

.. code:: javascript

    deleteAction() {
        this.allowMethods = 'delete';
        this.validateParamAction();
        let rules = {
            id: {
                required: true,
                int: {min: 1},
                method: 'get'
            }
        };

        const flag = this.validate(rules);
        if (!flag) {
            return this.raise(1006, this.validateErrors);
        }
    }


- controller/courseCategory.js

.. code:: javascript

    async deleteAction() {
        const {id} = this.get();
        const modelCourseCategory = think.getModel(MODEL_NAMES.COURSE_CATEGORY);

        await modelCourseCategory.where({id: id}).delete();

        this.success();
    }
          
.. warning::

    - 编辑/删除 数据时，要 **特别小心** ，如果是针对单条数据的，一定要 **限制好查询条件** ，以免变成 **批量** 操作

API 测试
-----------
- apizz.cc::

    简单的网页版API测试工具

- postMan::

    棒得很高的一款测试工具

- curl

- 其他，以后再介绍

