.. Copyright 2013 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with Remote webdriver
    :keywords: splinter, python, tutorial, how to install, installation, remote, selenium


++++++++++++++++
Remote WebDriver
++++++++++++++++

Remote WebDriver 由 Selenium2 提供。如果你要使用它, 请先通过pip安装 Selenium2:

.. highlight:: bash

::

    $ [sudo] pip install selenium

远程 WebDriver
-------------------------------

为了使用远程 web driver, 你需要访问 Selenium 远程 webdriver 服务器。本文档不介绍如何设置
服务器。不过有些公司会提供 `Selenium Grid`_ 作为服务器访问。


使用远程 WebDriver
--------------------------

为了使用远程 WebDriver，在实例化 ``Browser`` 时，你需要传入 ``driver_name="remote"`` 和 ``url=<remote server url>``。

你也可以通过传递与 Selenium `DesiredCapabilities`_ 参数对应的其他参数.

以下是当你使用 `Sauce Labs`_ (一个专门提供 Selenium 远程 webdriver 服务器的公司) 来请求
在 Windows 7 上运行的 Internet Explorer 9 浏览器实例的示例。

.. highlight:: python

::

    remote_server_url = ... # Specify the server URL

    with Browser(driver_name="remote",
                 url=remote_server_url,
                 browser='internetexplorer',
                 platform="Windows 7",
                 version="9",
                 name="Test of IE 9 on WINDOWS") as browser:
        print("Link to job: https://saucelabs.com/jobs/{}".format(
              browser.driver.session_id))
        browser.visit("https://splinter.readthedocs.io")
        browser.find_link_by_text('documentation').first.click()


.. _Selenium Grid: https://code.google.com/p/selenium/wiki/Grid2
.. _DesiredCapabilities: https://code.google.com/p/selenium/wiki/DesiredCapabilities
.. _Sauce Labs: https://saucelabs.com
