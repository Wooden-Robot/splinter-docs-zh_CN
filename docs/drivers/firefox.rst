.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with Firefox webdriver
    :keywords: splinter, python, tutorial, how to install, installation, firefox, selenium

+++++++++++++++++
Firefox WebDriver
+++++++++++++++++

.. module:: splinter.driver.webdriver.firefox

Firefox WebDriver由Selenium 2.0提供。要使用它，您需要通过pip安装Selenium 2.0：

.. highlight:: bash

::

    $ [sudo] pip install selenium


重要的是要注意，您还需要在机器中安装 `Firefox <http://firefox.com>`_ 和 `geckodriver <https://github.com/mozilla/geckodriver/releases>`_  并且可以在 `PATH` 环境变量中使用。
一旦你安装了，你没有什么你要做，就可以使用它:)

使用Firefox WebDriver
-----------------------

您只需要使用Firefox驱动程序，您只需要在 ``Browser`` 方法中写入传递 ``firefox`` 字符串：

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('firefox')

**注意：** 如果您在 ``Browser`` 方法中未写入驱动器程序名称，则默认使用 ``firefox`` 驱动方式。


使用 Firefox headless
-----------------------

从 Firefox 55开始, 我们可以在 Linux 系统上使用 Firefox headless。

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('firefox', headless=True)


如何使用Firefox的特定配置文件
-----------------------------------------

您可以用 ``Browser`` 方法中的 ``profile`` 关键词选项来设定 `Firefox 配置文件 <http://support.mozilla.com/en-US/kb/Profiles>`_
(以配置名称 ``字符串`` 形式作传递):

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('firefox', profile='my_profile')

如果不指定配置文件，将创建一个新的临时配置文件（并在 ``close`` 浏览器时删除）。

如何使用Firefox的扩展插件
------------------------------------------

firefox的扩展插件是.xpi类型的文件格式。要在Firefox webdriver配置文件中使用扩展插件，您需要使用extensions关键字选项（扩展插件以为 ``列表`` 形式作实例传递）来给出扩展插件路径：

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('firefox', extensions=['extension1.xpi', 'extension2.xpi'])

如果您使用了扩展程序，则在关闭浏览器后，即使不是临时扩展插件，扩展插件也将将从配置文件中删除。

How to use selenium capabilities for Firefox
--------------------------------------------

.. highlight:: python

::
    from splinter import Browser
    browser = Browser('firefox', capabilities={'acceptSslCerts': True})

You can pass any selenium `read-write DesiredCapabilities parameters <https://code.google.com/p/selenium/wiki/DesiredCapabilities#Read-write_capabilities>`_ for Firefox.


API文档
--------

.. autoclass:: WebDriver
   :members:
   :inherited-members:
