.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with Chrome webdriver
    :keywords: splinter, python, tutorial, how to install, installation, chrome, selenium

++++++++++++++++
Chrome WebDriver
++++++++++++++++

Chrome WebDriver 由 Selenium2 提供. 使用它需先通过 pip 安装 Selenium2：

.. highlight:: bash

::

    $ [sudo] pip install selenium

同时请确保你的电脑安装了谷歌浏览器.

我们可以在自定义路径中使用 Chrome，不过你需要将可执行路径作为字典传递给 `**kwargs` 参数. 将 `executable_path` 作为字典的key值，将可执行文件的路径设置为字典的Value。

.. highlight:: python

::

    from splinter import Browser
    executable_path = {'executable_path':'</path/to/chrome>'}

    browser = Browser('chrome', **executable_path)

设置 Chrome WebDriver
---------------------------

在 Splinter 中使用 `Google Chrome <http://google.com/chrome>`_ , 我们需要使用 Selenium 2.3.x, 同时
确保正确安装 Chrome webdriver。

Mac OS X
--------

推荐使用 `Homebrew <http://mxcl.github.com/homebrew/>`_ 进行安装:

.. highlight:: bash

::

    $ brew install chromedriver


Linux
-----

去 `Chromium 下载页面<https://code.google.com/p/chromedriver/downloads/list>`_ 根据你
的 Linux (32 or 64 位) 系统选择适合的版本。然后将解压后的文件移动到一个在 ``PATH`` 中的目录内
(比如 ``/usr/bin``)。你也可以将其解压在任何目录下
并将该目录添加到 ``PATH``:


Linux 32位
============

.. highlight:: bash

::

    $ cd $HOME/Downloads
    $ wget https://chromedriver.googlecode.com/files/chromedriver_linux32_20.0.1133.0.zip
    $ unzip chromedriver_linux32_20.0.1133.0.zip


Linux 64位
============

.. highlight:: bash

::

    $ cd $HOME/Downloads
    $ wget https://chromedriver.googlecode.com/files/chromedriver_linux64_20.0.1133.0.zip
    $ unzip chromedriver_linux64_20.0.1133.0.zip


Linux (32 和 64位通用步骤)
======================================

.. highlight:: bash

::

    $ mkdir -p $HOME/bin
    $ mv chromedriver $HOME/bin
    $ echo "export PATH=$PATH:$HOME/bin" >> $HOME/.bash_profile


Windows
-------

    **注意:** 对于 Windows 用户，我们暂不提供官方支持，但您可以自行尝试。

你只需要去 `Selenium 项目下载页面 <https://code.google.com/p/chromedriver/downloads/list>`_ 下载
"ChromeDriver server for win". 你的浏览器会下载 zip 文件, 解压并将这个 ``.exe`` 文件添加到 PATH 中。

如果您不知道如何向 Windows 的 PATH 添加可执行文件，请参考以下链接:

* `Environment variables <http://msdn.microsoft.com/en-us/library/ms682653.aspx>`_
* `How to manage environment variables in Windows XP <http://support.microsoft.com/kb/310519>`_


使用 Chrome WebDriver
----------------------

要使用 Chrome driver, 你只需要在创建 ``Browser`` 实例时传入字符串 ``chrome``：

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('chrome')

**注意:** 如果你不为 ``Browser`` 指定 driver, 那么会默认使用 ``firefox``。

**注意:** 如果你在使用 ``$HOME/.bash_profile`` 时遇到问题, 可以试试 ``$HOME/.bashrc``。

使用 Chrome headless
--------------------------------

从Chrome 59开始，我们可以运行 Chrome 作为一个 headless 浏览器。
使用前请阅读 `google developers updates <https://developers.google.com/web/updates/2017/05/nic59#headless>`_

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('chrome', headless=True)

使用 Chrome 仿真模式
------------------------------

可以通过 Chrome options 定制 Chrome 的模式，从而开启实验性的仿真模式。

.. highlight:: python

::

    from selenium import webdriver
    from splinter import Browser

    mobile_emulation = {"deviceName": "Google Nexus 5"}
    chrome_options = webdriver.ChromeOptions()
    chrome_options.add_experimental_option("mobileEmulation",
                                           mobile_emulation)
    browser = Browser('chrome', options=chrome_options)


详细内容请参考 `chrome driver documentation <https://sites.google.com/a/chromium.org/chromedriver/mobile-emulation>`_


API 文档
--------

.. autoclass:: splinter.driver.webdriver.chrome.WebDriver
   :members:
   :inherited-members:
