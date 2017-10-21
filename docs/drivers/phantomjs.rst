.. Copyright 2013 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with phantomjs webdriver
    :keywords: splinter, python, tutorial, how to install, installation, phantomjs, selenium

+++++++++++++++++++
Phantomjs WebDriver
+++++++++++++++++++

.. module:: splinter.driver.webdriver.phantomjs

PhantomJS 是一个基于 headless WebKit 的服务器端 JavaScript API, 使用之前你需要
`下载 <http://phantomjs.org/download.html>`_ 它到电脑中。
Phantomjs WebDriver 依赖于 Selenium 2.0，所以你需要使用 pip 安装 Selenium 2.0 版本:

.. highlight:: bash

::

    $ [sudo] pip install selenium

使用 Phantomjs WebDriver
-------------------------

你只需要在生成 ``Browser`` 实例时传入字符串 ``phantomjs`` 就可以使用 Phantomjs driver 了。

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('phantomjs')

**注意:** 如果你不为 ``Browser`` 指定 driver, 那么会默认使用 ``firefox``。

PhantomJS 也可以通过自定义路径来使用。你需要向 `**kwargs` 参数传入一个包含可执行路径的字典。
这个字典需要有一个 key 为 `executable_path`，value 为可执行文件路径的值。

.. highlight:: python

::

    from splinter import Browser
    executable_path = {'executable_path':'</path/to/phantomjs>'}

    browser = Browser('phantomjs', **executable_path)

API docs
--------

.. autoclass:: WebDriver
   :members:
   :inherited-members:
