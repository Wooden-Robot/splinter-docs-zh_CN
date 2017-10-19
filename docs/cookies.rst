.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Cookie manipulation
    :keywords: splinter, python, tutorial, documentation, cookies

++++++++++++++++++++
操控 Cookies
++++++++++++++++++++

可以通过 `Browser` 实例的 `cookies` 属性操控 cookies。`cookies` 属性是可以增加和删除 cookie 的 `CookieManager` 类的一个实例。

创建 cookie
-------------

使用 `add` 方法增加一个 cookie：

.. highlight:: python

::

    browser.cookies.add({'whatever': 'and ever'})

获取所有的 cookies
--------------------

使用 `all` 方法获取所有的 cookies:

.. highlight:: python

::

    browser.cookies.all()

删除一个 cookie
---------------

你可以通过 ``delete`` 方法删除一个或者更多的 cookies:

.. highlight:: python

::

    browser.cookies.delete('mwahahahaha')  # 删除 'mwahahahaha' 这个 cookie
    browser.cookies.delete('whatever', 'wherever')  # 删除两个 cookies

删除所有的 cookies
------------------

不要任何参数，仅仅需要调用 ``delete`` 方法就可以删除所有的 cookies：

.. highlight:: python

::

    browser.cookies.delete()  # 删除所有的 cookies

更多信息请参考
:class:`CookieManager <splinter.cookie_manager.CookieManagerAPI>` 类的 API 文档。
