.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Finding elements
    :keywords: splinter, python, tutorial, find, selectors

++++++++++++++++
查找元素
++++++++++++++++

Splinter提供了6种方法用于查找在页面中的元素，并用于每个选择器类型：: ``css``, ``xpath``, ``tag``, ``name``, ``id``, ``value``,
``text``.
例如:

.. highlight:: python

::

    browser.find_by_css('h1')
    browser.find_by_xpath('//h1')
    browser.find_by_tag('h1')
    browser.find_by_name('name')
    browser.find_by_text('Hello World!')
    browser.find_by_id('firstheader')
    browser.find_by_value('query')


这些方法中的每一个返回一个包含已找到元素的列表。您可以使用 ``first`` 快捷方式获取第一个找到的元素：

.. highlight:: python

::

    first_found = browser.find_by_name('name').first

还有last快捷方式 ，它返回最后发现的目标元素：

.. highlight:: python

::

    last_found = browser.find_by_name('name').last

使用索引获取元素
=======================

您还可以使用索引，在所找到的元素列表中获取所需的元素：

.. highlight:: python

::

    second_found = browser.find_by_name('name')[1]

所有元素和 ``find_by_id``
===============================

一个网页应该只有一个id，所以该 ``find_by_id`` 方法总是只返回一个元素的列表。

查找链接
=============

如果你需要找到一个页面的链接，你可以使用以下方法：
``find_link_by_text``, ``find_link_by_partial_text``, ``find_link_by_href`` or
``find_link_by_partial_href``. 举例：

.. highlight:: python

::

    links_found = browser.find_link_by_text('Link for Example.com')
    links_found = browser.find_link_by_partial_text('for Example')
    links_found = browser.find_link_by_href('http://example.com')
    links_found = browser.find_link_by_partial_href('example')


作为其他 ``find_*`` 方法，它们返回所有找到的元素的列表。

您还可以搜索使用其他类型的选择与方法：
``find_by_css``, ``find_by_xpath``, ``find_by_tag``, ``find_by_name``,
``find_by_value`` 和 ``find_by_id``.

链式查找元素
=========================

查找方法是可链式的，因此您可以找到先前发现的元素的后续属性。

.. highlight:: python

::

    divs = browser.find_by_tag("div")
    within_elements = divs.first.find_by_name("name")

``ElementDoesNotExist`` 异常处理
=================================

如果未找到元素，则 ``find_*`` 返回空列表。但是，如果您尝试访问此列表中的元素，该方法将触发 `splinter.exceptions.ElementDoesNotExist` 异常。
