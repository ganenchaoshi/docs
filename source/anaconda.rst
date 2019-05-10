
anaconda笔记
-------------

install
-------------

常用命令
--------
创建制定python版本的环境

.. code::

    conda create -n envpy27
    conda create -n envpy27 python=2.7
    conda create --name envpy27 python=2.7
    创建包含某些包的环境
    conda create --name your_env_name python=3.5 numpy scipy

.. code:: python

    class test():
        def __init__():
            self.test = true

        def test():
            print('test method')
    

Linux:
    source activate your_env_name(虚拟环境名称)
    source deactivate

列举当前所有环境
conda info --envs
conda env list

conda deactivate
conda activate envpy27


复制某个环境
conda create --name new_env_name --clone old_env_name

删除某个环境
conda remove --name your_env_name --all

列举当前活跃环境下的所有包
conda list

列举一个非当前活跃环境下的所有包
conda list -n your_env_name

分享环境，通过导出环境文件
    以envpy27这个环境为例
    $activate envpy27
    $conda env export > environment.yml
    $conda env create -f environment.yml

为指定环境安装某个包

conda install -n env_name package_name

flake8
isort
yapf

who are you ?
---====~~~#****
conda install matplotlib

conda update matplotlib

conda remove matplotlib

Python：Anaconda创建、激活、换源、退出、删除虚拟环境
https://blog.csdn.net/zuliang001/article/details/83042892

换源:
    ~/.condarc

    C:\Users\当前用户名.condarc

提高下载速度

Anaconda 的镜像地址默认在国外，用 conda 安装包的时候会很慢，目前可用的国内镜像源地址是清华大学提供的。修改 ~/.condarc (Linux/Mac) 或 C:\Users\当前用户名.condarc (Windows) 配置
.. :code::
    channels:
    
    - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    
    - defaults
 
show_channel_urls: true
除此之外，你也可以把 pip 的镜像源地址也换成国内的，豆瓣源速度比较快。修改 ~/.pip/pip.conf (Linux/Mac) 或 C:\Users\当前用户名\pip\pip.ini (Windows) 配置：

[global]
 
trusted-host = pypi.douban.com
 
index-url = http://pypi.douban.com/simple
--------------------- 
作者：会飞的小罐子 
来源：CSDN 
原文：https://blog.csdn.net/qq_38150441/article/details/81083469 
版权声明：本文为博主原创文章，转载请附上博文链接！