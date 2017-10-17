.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Splinter tutorial, learn how to test your web applications
    :keywords: splinter, python, tutorial, documentation, web application, tests, atdd, tdd, acceptance tests

+++++++++++++++++
Splinter 教程
+++++++++++++++++

开始之前, 确认已经 :doc:`安装 </install>` Splinter

以下教程通过一个简单的例子一步一步教你如何使用 Splinter：

* 通过 baidu.com 搜索 ``splinter - python acceptance testing for web applications``，
* 查找 Splinter 官方网站是否在搜索结果中。

创建一个 Browser 实例
=========================

首先, 导入 ``Browser`` 类并创建一个实例。

.. highlight:: python

::

    from splinter import Browser
    browser = Browser()
    # 指定driver为chrome浏览器
    # browser = Browser(driver_name='chrome')

**注意:** 如果你不为 ``Browser`` 指定 driver, 那么会默认使用 ``firefox``.


访问百度搜索页面
====================

使用 ``browser.visit`` 方法可访问任意网站. 让我们访问一下百度搜索页面:

.. highlight:: python

::

    browser.visit('http://baidu.com')


输入搜索关键词
=================

页面加载完毕后，你能进行一系列的交互，比如点击，输入框填充字段，选择单选按钮和复选框。让我们在百度搜索框中填充 ``splinter - python acceptance testing for web applications``。

.. highlight:: python

::

    browser.fill('wd', 'splinter - python acceptance testing for web applications')

点击搜索按钮
=======================

告诉 Splinter 哪一个按钮需要点击。这个按钮 - 或任意其他元素 - 可以通过它的css, xpath, id, tag 或 name来识别。

通过以下操作找到百度搜索按钮：

.. highlight:: python

::

    button = browser.find_by_xpath('//input[@type="submit"]')

提示一下，这个 ``//input[@type="submit"]`` xpath 语法所在的按钮会在百度搜索页面的源码中被找到。

找到按钮后，我们就可以进行点击操作:

.. highlight:: python

::

    button.click()


注意: 以上展示的两步可以结合为一行代码，如下所示:

.. highlight:: python

::

    browser.find_by_xpath('//input[@type="submit"]').click()


查看 Splinter 官方网站是否在搜索结果中
================================================================

点击搜索按钮后，你可以通过以下步骤检测 Splinter 官方网站是否在搜索结果中。

.. highlight:: python

::

    if browser.is_text_present('splinter.readthedocs'):
        print "Yes, found it! :)"
    else:
        print "No, didn't find it :("


在这个小例子中, 我们只是打印出了结果. 当写测试的时候，你需要使用断言。

关闭浏览器
=================

结束测试后，我们需要使用 ``browser.quit`` 关闭浏览器:

.. highlight:: python

::

    browser.quit()

总结
============

最后完整的代码如下所示:

.. highlight:: python

::

    from splinter import Browser

    browser = Browser()
    browser.visit('http://baidu.com')
    browser.fill('wd', 'splinter - python acceptance testing for web applications')
    button = browser.find_by_xpath('//input[@type="submit"]').click()

    if browser.is_text_present('splinter.readthedocs'):
        print "Yes, the official website was found!"
    else:
        print "No, it wasn't found... We need to improve our SEO techniques"

    browser.quit()

