.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Executing javascript 
    :keywords: splinter, python, tutorial, javascript

++++++++++++++++++++
执行 javascript
++++++++++++++++++++

如果 driver 可执行 javascript，那么你可以通过下面的例子很方便地执行 javascript 代码：

.. highlight:: python

::

    browser.execute_script("$('body').empty()")

你可以获取到执行脚本后返回的值:

.. highlight:: python

::

    browser.evaluate_script("4+4") == 8


