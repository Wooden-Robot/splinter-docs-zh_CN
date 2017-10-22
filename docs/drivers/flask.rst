.. Copyright 2014 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with Flask.
    :keywords: splinter, python, tutorial, how to install, installation, Flask

++++++++++++
Flask客户端
++++++++++++

.. module:: splinter.driver.flaskclient

要使用 ``flask`` 驱动, 你需要安装 `Flask <https://pypi.python.org/pypi/Flask>`_, 
`lxml <https://pypi.python.org/pypi/lxml>`_ 和 `cssselect <http://pypi.python.org/pypi/cssselect>`_. 
您可以通过运行以下步骤一次安装它们：

.. highlight:: bash

::

    $ pip install splinter[flask]

使用Flask客户端
-------------------

使用 ``flask`` 驱动,您需要在创建 ``Browser`` 实例时，需要填入 ``flask`` 字符串和设定关键词参数 ``app`` ：

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('flask', app=app)

**注意：** 如果您不提供任何驱动程序模式字符串给 ``Browser`` 方法，``firefox`` 将被默认使用。

API文档
--------

.. autoclass:: FlaskClient
   :members:
   :inherited-members:
