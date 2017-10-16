.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Install guide for splinter
    :keywords: splinter, python, tutorial, how to install, installation

+++++++++++++
安装指南
+++++++++++++

安装 Python
==============

安装Splinter之前，请确保电脑系统中已经安装了Python。注意：Splinter仅支持Python2.7以上版本。

您可从Python官方网站 http://www.python.org 下载Python。如果您使用的是类Linux或Mac OS X系统，则可能已经安装。

安装 splinter
================

基本上有两种方式来安装Splinter：

安装稳定版本
------------------------

如果您对官方和几乎无错的版本感兴趣，只需从终端运行：


.. highlight:: bash

::

	$ [sudo] pip install splinter



安装最新测试版本
-------------------------------------

如果您想使用Splinter的最新功能，并且不怕在自己的开发代码下运行，请运行：

.. highlight:: bash

::

    $ git clone git://github.com/cobrateam/splinter.git
    $ cd splinter
    $ [sudo] python setup.py install


**注意：**

    * - 确保您已经 :doc:`设置了您的开发环境 </contribute/setting-up-your-development-environment>`.
    * - 请确保已安装 `Git <http://git-scm.com/>`_ .
    * - 为了使用Chrome浏览器，您需要 :doc:`正确设置Chrome </drivers/chrome>`.
