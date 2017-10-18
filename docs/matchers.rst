.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Checking if a text pattern is or not present
    :keywords: splinter, python, tutorial, element

++++++++
Matchers
++++++++

当使用AJAX和异步 JavaScript 时，通常会出现HTML源代码中不存在的元素（它们是由 JavaScript 动态生成）。
在这种情况下，您可以使用 ``is_element_present`` 和 ``is_text_present`` 方法来检查元素或
文本是否存在 -- Splinter 将在浏览器中加载 HTML 和 JavaScript，并在运行 JavaScript *之前* 进行检查。

还有一个可选参数 ``wait_time`` (以秒为单位) -- 这是一个超时选项: 如果验证方法得到 ``True``
它将返回结果 (即使时间没有超过 ``wait_time`` ), 如果没有得到 ``True``, 该方法将等待直到时间
超过 ``wait_time`` ，然后返回结果。


检查文本是否存在
-----------------------------

``is_text_present`` 方法负责检查页面内容中是否存在特定文本。存在返回 ``True``，不存在返回 ``False``。

.. highlight:: python

::

    browser = Browser()
    browser.visit('https://splinter.readthedocs.io/')
    browser.is_text_present('splinter') # True
    browser.is_text_present('splinter', wait_time=10) # True, using wait_time
    browser.is_text_present('text not present') # False


还有一种方法来检查文本 *不存在* : ``is_text_not_present`` 。 工作原理相同相同，但如果文本不存在则返回 ``True`` 。
is not present.

.. highlight:: python

::

    browser.is_text_not_present('text not present') # True
    browser.is_text_not_present('text not present', wait_time=10) # True, using wait_time
    browser.is_text_not_present('splinter') # False


检查元素是否存在
---------------------------------

Splinter 提供了6种方法来检查页面元素是否存在, 与这些选择器一一对应: ``css``, ``xpath``,
``tag``, ``name``, ``id``, ``value``, ``text``。 例如:

.. highlight:: python

::

    browser.is_element_present_by_css('h1')
    browser.is_element_present_by_xpath('//h1')
    browser.is_element_present_by_tag('h1')
    browser.is_element_present_by_name('name')
    browser.is_element_present_by_text('Hello World!')
    browser.is_element_present_by_id('firstheader')
    browser.is_element_present_by_value('query')
    browser.is_element_present_by_value('query', wait_time=10) # using wait_time

正如预想的那样，如果元素存在，这些方法会返回 ``True`` ，如果元素不存在则返回 ``False`` 。

和 ``is_text_present`` 类似，上述方法也都存在着相反的方法:

.. highlight:: python

::

    browser.is_element_not_present_by_css('h6')
    browser.is_element_not_present_by_xpath('//h6')
    browser.is_element_not_present_by_tag('h6')
    browser.is_element_not_present_by_name('unexisting-name')
    browser.is_element_not_present_by_text('Not here :(')
    browser.is_element_not_present_by_id('unexisting-header')
    browser.is_element_not_present_by_id('unexisting-header', wait_time=10) # using wait_time
