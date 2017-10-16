.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Documentation for splinter, an open source tool for testing web applications
    :keywords: splinter, python, tutorial, documentation, web application, tests, atdd, tdd, acceptance tests

Splinter
==============

Splinter 是用 Python 开发的一个开源web自动化测试的工具集。
它可以帮你自动化浏览器的行为，比如浏览 URLs 并和页面进行交互。

简单的例子
-----------

.. highlight:: python

::
    from splinter import Browser

    with Browser() as browser:
        # 访问 URL
        url = "http://baidu.com"
        browser.visit(url)
        browser.fill('wd', 'splinter - python acceptance testing for web applications')
        # 找到并点击搜索按钮
        button = browser.find_by_xpath('//input[@type="submit"]')
        # 与元素交互
        button.click()

        if browser.is_text_present('splinter.readthedocs'):
            print "Yes, the official website was found!"
        else:
            print "No, it wasn't found... We need to improve our SEO techniques"

**提示:** 如果你不为 ``Browser`` 指定 driver, 那么会默认使用 ``firefox``。

特点
--------

* 简单的 api
* 支持多种 webdriver (chrome webdriver, firefox webdriver, phantomjs webdriver, zopetestbrowser, remote webdriver)
* 支持 css 和 xpath 选择器
* 支持 iframe 和 alert
* 可执行 javascript 脚本
* 支持 ajax 和 异步 javascript

:doc:`Splinter 有什么新特性? </news>`

开始上手
---------------
* :doc:`为什么使用 Splinter </why>`
* :doc:`安装 </install>`
* :doc:`快速上手 </tutorial>`

基础的浏览和交互
-------------------------------

* :doc:`Browser and navigation </browser>`
* :doc:`Finding elements </finding>`
* :doc:`Mouse interactions </mouse-interaction>`
* :doc:`Interacting with elements and forms </elements-in-the-page>`
* :doc:`Verify the presence of texts and elements in a page, with matchers </matchers>`
* :doc:`Cookies manipulation </cookies>`

支持 JavaScript
------------------

* :doc:`运行 JavaScript 脚本</javascript>`

继续...
-------------

* :doc:`处理 HTTP 状态码和异常 </http-status-code-and-exception>`
* :doc:`与 iframes, alerts 和 prompts 互动 </iframes-and-alerts>`

Drivers
-------

常用浏览器 drivers
+++++++++++++++++++++

The following drivers open a browser to run your actions:

* :doc:`Chrome WebDriver </drivers/chrome>`
* :doc:`Firefox WebDriver </drivers/firefox>`
* :doc:`Remote WebDriver </drivers/remote>`

无界面浏览器 drivers
++++++++++++++++

The following drivers don't open a browser to run your actions (but has its own dependencies, check the
specific docs for each driver):

* :doc:`Chrome WebDriver </drivers/chrome>`
* :doc:`Phantomjs WebDriver </drivers/phantomjs>`
* :doc:`zope.testbrowser </drivers/zope.testbrowser>`
* :doc:`django client </drivers/django>`
* :doc:`flask client </drivers/flask>`

远程 driver
++++++++++++++

The remote driver uses Selenium Remote to control a web browser on a remote
machine.

* :doc:`远程 WebDriver </drivers/remote>`


Get in touch and contribute
===========================

* :doc:`Community </community>`
* :doc:`Contribute </contribute>`
* :doc:`Writing new drivers </contribute/writing-new-drivers>`
* :doc:`Setting up your splinter development environment </contribute/setting-up-your-development-environment>`
