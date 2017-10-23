.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Finding elements
    :keywords: splinter, python, tutorial, screenshot

++++++++++++++++++
截图
++++++++++++++++++

Splinter 本身并不支持截图，你必须使用 driver 的 `take_screenshot` 方法进行截图。

.. highlight:: python

::

    browser = Browser()
    browser.driver.save_screenshot('your_screenshot.png')
