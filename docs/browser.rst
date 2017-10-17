.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Browser
    :keywords: splinter, python, tutorial, browser, firefox, chrome, zope, testebrowser

+++++++
浏览器
+++++++

要使用splinter，您需要创建一个Browser实例：

.. highlight:: python

::

    from splinter import Browser
    browser = Browser()

或者利用 ``context manager`` （上下文管理器）形式, 即通过 ``with`` 语句来实现:

.. highlight:: python

::

    from splinter import Browser
    with Browser() as b:
        # stuff using the browser

最后一个例子将会创建一个新的浏览器窗口，当光标到达 ``with`` 声明语句外部时关闭它。

splinter支持三种驱动程序：chrome，firefox和zopetestbrowser。

.. highlight:: python

::

    browser = Browser('chrome')
    browser = Browser('firefox')
    browser = Browser('zope.testbrowser')

=============================
用Browser.visit浏览
=============================

您可以使用该 ``visit`` 方法导航到其他页面：

.. highlight:: python

::

    browser.visit('https://baidu.com')

该 ``visit`` 方法只需要 ``url`` 这一个参数来访问。

您可以通过在URL中提供用户名和密码来访问受HTTP身份验证保护的站点。

::

    browser.visit('http://username:password@xxxx.xx/protected')

================
管理页面窗口
================

您可以通过Windows对象来管理多个窗口（如弹出窗口）：

.. highlight:: python

::

    browser.windows              # 获取全部窗口
    browser.windows[0]           # 获取第一个窗口
    browser.windows[window_name] # 获取指定窗口名的窗口
    browser.windows.current      # 获取当前窗口
    browser.windows.current = browser.windows[3]  # 设置当前窗口索引号为3

    window = browser.windows[0]
    window.is_current            # 布尔判断 - 窗口是否为当前活动窗口
    window.is_current = True     # 设置窗口为当前窗口
    window.next                  # 下一个窗口
    window.prev                  # 上一个窗口
    window.close()               # 关闭窗口
    window.close_others()        # 关闭所有其他窗口

此窗口管理界面方法不兼容 splinter v0.6.0及更早版本。

=============
重新加载页面
=============

您可以使用 ``reload`` 方法重新加载页面：

.. highlight:: python

::

    browser.reload()

============================
浏览历史
============================

您可以使用 ``back`` 和 ``forward`` 方法来浏览历史记录:

.. highlight:: python

::

    browser.visit('http://cobrateam.info')
    browser.visit('https://splinter.readthedocs.io')
    browser.back()
    browser.forward()

=============
Browser.title
=============

您可以使用以下 ``title`` 属性获取访问页面的标题：

.. highlight:: python

::

    browser.title

========================================
使用Browser.html验证页面内容
========================================

您可以使用该 ``html`` 属性来获取访问页面的html内容：

.. highlight:: python

::

    browser.html

===================================
使用Browser.url验证页面网址
===================================

访问页面的URL可以通过 ``url`` 属性访问：

.. highlight:: python

::

    browser.url

===========================
更改浏览器User-Agent
===========================

您可以在浏览器实例化时传递User-Agent。

.. highlight:: python

::

    b = Browser(user_agent="Mozilla/5.0 (iPhone; U; CPU like Mac OS X; en)")
