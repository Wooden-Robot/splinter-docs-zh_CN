.. Copyright 2012 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Automatic interaction with alerts, prompts and iframes
    :keywords: splinter, python, tutorial, alerts, prompts, iframes, acceptance tests

++++++++++++++++++++++++++
Frames, alerts 和 prompts
++++++++++++++++++++++++++

使用 iframes
-------------

你可以通过 ``get_iframe`` 方法和 ``with`` 声明与 iframes 进行交互。你可以向 ``get_iframe`` 方法传出 iframe 的 name, id, 或者 index 来获取 iframe。

.. highlight:: python

::

    with browser.get_iframe('iframemodal') as iframe:
        iframe.do_stuff()


处理 alerts 和 prompts
---------------------------

    从 Splinter 0.4版本开始，Chrome 浏览器支持与 alerts 和 prompts 的交互。

**注意:** 只有 Firefox 和 Chrome 支持与 alerts 和 prompts 进行交互。

你可以使用 ``get_alert`` 方法来处理 alerts 和 prompts。

.. highlight:: python

::

    alert = browser.get_alert()
    alert.text
    alert.accept()
    alert.dismiss()


对于 prompts, 你可以使用 ``fill_with`` 方法进行回复。

.. highlight:: python

::

    prompt = browser.get_alert()
    prompt.text
    prompt.fill_with('text')
    prompt.accept()
    prompt.dismiss()


你也可以使用 ``with`` 声明同时与 alerts 和 prompts 进行交互。

.. highlight:: python

::

    with browser.get_alert() as alert:
        alert.do_stuff()

如果页面没有 prompt 或者 alert，``get_alert`` 会返回 ``None``。
记住至少要使用一个 alert/prompt 的结束方法(accept 和 dismiss)。
否则你的浏览器会处于休眠状态不能进行其他操作，除非你对 alert/prompt 正确地选择了accept 或者 dismiss。
