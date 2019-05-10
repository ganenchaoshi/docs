install
-----------

$conda/pip install sphinx

$conda/pip install sphinx_rtd_theme

$conda/pip install doc8

$sphinx-quickstart，默认一路回车，应该有有用的配置可启用，conf.py中有涉及

$make html

如何用 ReadtheDocs、Sphinx 快速搭建写书环境
https://www.jianshu.com/p/78e9e1b8553a

配置
-----------
conf.py
    html_theme = 'sphinx_rtd_theme'

概念
======
首先明确 reStructuredText 里的几个基本知识点（为了便于理解，不严谨）：

    #. 标记元素分两种：指令（Directives）和角色（Role），指令是块级元素，像段落一样使用。角色是行内元素，可以写在普通文本之中。
    #. 指令和它要包含的内容之间需要一个空行。
    #. 几组特殊符号：\ `` .. : 和空格。
    #. 空行、空格和缩进都是有意义的，你在其他语法中可能会遇到自动清除缩进的情况，但在 reStructuredText 里是讲究对齐缩进的。
    #. 每级缩进推荐用 4 个空格，你可以把你的编辑器设置为 Tab 自动转为 4 个空格。
    #. 块级元素可以用缩进来嵌套，除了标题（标题是一种特殊的块级元素，不能放在缩进的文本中）。
    #. 行内元素虽然有些可以嵌套，但极不推荐。[1]

    | 如果只是想段内换行，不加序号或无序符号，则行首用“|” + 空格
    | haha
    | xixi
    .. note::
        haha

常用语法
-----------
标题
======


段落
======
段落通过空行来实现:
    1.同样缩进的情况下
        如果行尾仅仅是换行
        不空行，则换行处会与下一行通过一个空隔相连；
        
        如果不希望有空格，则在换行处加\
        即可无缝相连

标记
======

图片
======

表格
======

链接
======

代码
======

测试一下

行内代码
~~~~~~~~

测试2

原始文本块
~~~~~~~~~~

测试3

块级代码
~~~~~~~~

测试4

如何用 ReadtheDocs、Sphinx 快速搭建写书环境
https://www.jianshu.com/p/78e9e1b8553a

doc8: Windows 下使用 VSCode 编辑 *.rst 文件的错误提示
https://kaffa.im/vscode-restructuredtext.html
https://www.twblogs.net/a/5bc213fc2b717711c924917a/zh-cn

#. parent list
    #. haha
    #. xixi

.. code::

    └─docs
        ├─.vscode
        ├─_build
        │  ├─doctrees
        │  └─html
        │      ├─.doctrees
        │      ├─_sources
        │      └─_static
        │          ├─css
        │          ├─fonts
        │          │  ├─Lato
        │          │  └─RobotoSlab
        │          └─js
        ├─_static
        └─_templates