.. Copyright 2014 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with django.
    :keywords: splinter, python, tutorial, how to install, installation, django

++++++++++++++++
django客户端
+++++++++++++

.. module:: splinter.driver.djangoclient

要使用 ``django`` 驱动, 你需要安装 `django <http://pypi.python.org/pypi/django>`_, 
`lxml <https://pypi.python.org/pypi/lxml>`_ 和 `cssselect <http://pypi.python.org/pypi/cssselect>`_. 
您可以通过运行以下步骤一次安装它们:

.. highlight:: bash

::

    $ pip install splinter[django]

使用django客户端
-------------------

使用 ``django`` 驱动, 即在创建``Browser``实例时，填入 ``django`` 字符串:

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('django')

**注意:** 如果不提供任何驱动模式字符串到``Browser``函数中，则``firefox``将默认使用

API文档
--------

.. autoclass:: DjangoClient
   :members:
   :inherited-members:
