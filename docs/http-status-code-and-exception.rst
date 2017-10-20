.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Dealing with HTTP status code and HTTP exceptions with Splinter
    :keywords: splinter, python, tutorial, documentation, exception, http error, status code

++++++++++++++++++++++++++++++++++++++++++++
处理HTTP状态代码和异常
++++++++++++++++++++++++++++++++++++++++++++

处理HTTP状态代码
-----------------------------

还可以检查browser.visit获取的HTTP状态代码。您可以使用 ``status_code.is_success`` 为您做的工作，或者您可以直接比较状态代码：

.. highlight:: python

::

    browser.visit('https://baidu.com')
    browser.status_code.is_success() # True
    # or
    browser.status_code == 200 # True
    # or
    browser.status_code.code # 200

这些方法的区别在于，如果您获得重定向（某些情况或许不是HTTP出错）， ``status_code.is_success`` 则会将您的响应视为成功。可以通过 ``status_code.code``  访问数字状体代码。

处理HTTP异常
------------------------

每当使用访问方法时，Splinter将检查响应是否成功，如果不是，则会引发HttpResponseError异常。但别担心，你可以很容易地捕获它：

.. highlight:: python

::

    try:
        browser.visit('http://cobrateam.info/i-want-cookies')
    except HttpResponseError, e:
        print "Oops, I failed with the status code %s and reason %s" % (e.status_code, e.reason)

..

    **注意:**  ``status_code`` 和HTTP异常处理仅适用于selenium webdriver。
