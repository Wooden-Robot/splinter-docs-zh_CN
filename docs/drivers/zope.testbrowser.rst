.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with zope.testbrowser
    :keywords: splinter, python, tutorial, how to install, installation, zope, testbrowser, zope.testbrowser

++++++++++++++++
zope.testbrowser
++++++++++++++++

.. module:: splinter.driver.zopetestbrowser

使用 ``zope.testbrowser`` driver, 你需要安装 `zope.testbrowser <http://pypi.python.org/pypi/zope.testbrowser>`_, `lxml <https://pypi.python.org/pypi/lxml>`_ 和 `cssselect <http://pypi.python.org/pypi/cssselect>`_. 你可以通过下列命令一步安装它们:

.. highlight:: bash

::

    $ pip install splinter[zope.testbrowser]

使用 zope.testbrowser
----------------------

你只需要在生成 ``Browser`` 实例时传入字符串 ``zope.testbrowser`` 就可以使用 ``zope.testbrowser`` 了。

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('zope.testbrowser')

为了防止访问过多的站点 ``zope.testbrowser`` 默认遵循 robots.txt。如果你绕开 robots 协议，可以使用下列方法：

.. highlight:: python

::

    browser = Browser('zope.testbrowser', ignore_robots=True)

**注意:** 如果你不为 ``Browser`` 指定 driver, 那么会默认使用 ``firefox``。

API docs
--------

.. autoclass:: ZopeTestBrowser
   :members:
   :inherited-members:
