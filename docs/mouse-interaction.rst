.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Mouse interatcion.
    :keywords: splinter, python, tutorial, documentation, mouse interaction, mouseover, mouseout, double click, mouse events

++++++++++++++++++
鼠标交互
++++++++++++++++++

    **注意:** 大部分鼠标交互目前仅适用于Chrome driver和火狐浏览器27.0.1

Splinter提供了一些鼠标与页面元素交互的方法。
这个功能有助于测试一个元素是否在鼠标移来时出现，移走时消失（例如：子菜单）。

你也可以对这个元素执行单击，双击或者右击操作。

举个简单例子: 假设你有这样一个 `jQuery <http://jquery.com>`_ 方法让鼠标移过来、移走:

.. highlight:: js

::

    $('.menu-links').mouseover(function(){
        $(this).find('.subitem').show();
    });

    $('.menu-links').mouseout(function(){
        $(this).find('.subitem').hide();
    });

你完全可以使用 Splinter 通过程序触发事件：

.. highlight:: python

::

    browser.find_by_css('.menu-links').mouse_over()
    # 检测子菜单是否出现...
    browser.find_by_css('.menu-links').mouse_out()


可以通过下列方法实现鼠标交互:

``移过来``
--------------

.. highlight:: python


将鼠标移到元素上方，例如:

::

    browser.find_by_tag('h1').mouse_over()


``移走``
-------------

.. highlight:: python

将鼠标从元素上移走，例如:

::

    browser.find_by_tag('h1').mouse_out()

``点击``
---------

.. highlight:: python

点击元素，例如:

::

    browser.find_by_tag('h1').click()

``双击``
----------------

.. highlight:: python

双击元素，例如:

::

    browser.find_by_tag('h1').double_click()

``右击``
---------------

.. highlight:: python

右击元素，例如:

::

    browser.find_by_tag('h1').right_click()

``拖放``
-----------------

你可以拖动一个元素并将其放在另外一个元素上，下面例子将 ``<h1>...</h1>`` 元素拖放到容器元素中
(由一个 CSS 类识别).

.. highlight:: python

::

    draggable = browser.find_by_tag('h1')
    target = browser.find_by_css('.container')
    draggable.drag_and_drop(target)
