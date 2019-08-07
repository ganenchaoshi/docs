test
--------

+---------------------------------------------+-------------------------+------------------+----------+
|            Header row, column 1             |        Header 2         |     Header 3     | Header 4 |
|           (header rows optional)            |                         |                  |          |
+=============================================+=========================+==================+==========+
| body row 1, column 1                        | column 2                | column 3         | column 4 |
+---------------------------------------------+-------------------------+------------------+----------+
| body row 2                                  | Cells may span columns. |                  |          |
+---------------------------------------------+-------------------------+------------------+----------+
| body row 3                                  | Cells may               | - Table cells    |          |
| +------------------------+  --+-- - contain |                         |                  |          |
| body row 4                                  | span rows.              | - body elements. |          |
+---------------------------------------------+-------------------------+------------------+----------+

============  ==========  ===
 assdfsfsd    afddffsdfs   s
============  ==========  ===
aaaaasdfasdf  aaaaa       sss
============  ==========  ===
asdfsdf       aa
============  ==========  ===


*说明性文字*

`解释文字`

``原样文本``


`中文或词组`_

中文或词组


.. _testLabel:

交叉索引的位置
===============

章节内容.

需引用自身, 查看 :ref:`testLabel`. 这里 ``ref_lable_name`` 无下开头的划线


参考式链接
===========

欢迎访问 `reStructuredText 结构化文本`_ 官方主页。

.. _`reStructuredText 结构化文本`: http://docutils.sf.net/

如果文档中多个链接指向的其实是同一地址，可以简略点只写一次：

Python_ 是 `我最喜欢的编程语言`_ 。用英语来说，就是 `my favorite programming language`_ 。

数学公式
==============
reStructuredText 的数学公式书写通过指令（Directives）： math 完成。如需网页上显示的话，则和其它所有标记语言一样需要引入 MathJax 或 KaTex js 库。

.. math::

   \alpha _t(i) = P(O_1, O_2, \ldots  O_t, q_t = S_i \lambda )
αt(i)=P(O1,O2,…Ot,qt=Siλ)
行内数学公式 则是通过 math role 实现的：

该圆的面积为 :math:`A_\text{c} = (\pi/4) d^2`.

.. _Python:
.. _`最喜欢的编程语言`:
.. _`my favorite programming language`: http://www.python.org/

行内式链接
============
当然在文档中使用行内式链接也是可以的。直接在文档中插入简单链接： http://docutils.sf.net/ 。如果 URL 地址中含有特殊字符甚至是中文，则使用尖括号将其括住：

<http://docutils.sf.net/>
也可以自定义链接文本：

`Python 编程语言 <http://www.python.org/>`_ 其实也有一些缺陷。

自动标题链接
================
reStructuredText 文档的各级标题（Sections）会自动生成链接，就像 GFM 风格的 Markdown 标记语言一样。这在 reStructuredText 语法手册中被称为“隐式链接（Implicit Hyperlink）”。无论名称为何，我们将可以在文档中快速跳转到其它小节（Sections）：

本小节内容应该与 `自动标题链接`_ 结合学习。

脚注
======
脚注 [#]_


就像这样创建一个脚注 [#]_ 。


.. [#] haha
.. [#] 这里是 **脚注** 的 *文本* 。

    .. note::
        脚注自动编号时，注意保持脚注和脚注内容的相对位置。当然你也可以直接指定使用特定数字，就像这样： [1]_ 。

.. `中文或词组`: http://w.1.cn

a



http://w.1.cn/?t=哈哈

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
参考
    https://sphinx-rtd-theme.readthedocs.io/en/stable/configuring.html#theme-options

    https://docs.readthedocs.io/en/latest/intro/getting-started-with-sphinx.html
    
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

