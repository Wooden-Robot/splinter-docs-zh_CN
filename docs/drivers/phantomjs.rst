.. Copyright 2013 splinter authors. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: How to use splinter with phantomjs webdriver
    :keywords: splinter, python, tutorial, how to install, installation, phantomjs, selenium

+++++++++++++++++++
Phantomjs WebDriver
+++++++++++++++++++

.. module:: splinter.driver.webdriver.phantomjs

PhantomJS is a headless WebKit scriptable with a JavaScript API, to use the driver first you must
`install <http://phantomjs.org/download.html>`_ it in your machine.
The Phantomjs WebDriver is provided by Selenium 2.0, thus you need to install Selenium 2.0 via pip:

.. highlight:: bash

::

    $ [sudo] pip install selenium

Using Phantomjs WebDriver
-------------------------

To use the Phantomjs driver, all you need to do is pass the string ``phantomjs`` when you create
the ``Browser`` instance:

.. highlight:: python

::

    from splinter import Browser
    browser = Browser('phantomjs')

**Note:** if you don't provide any driver to ``Browser`` function, ``firefox`` will be used.

PhantomJS can also be used from a custom path. To do this pass the executable path as a dictionary to the `**kwargs` argument. The dictionary should be set up with `executable_path` as the key and the value set to the path to the executable file.

.. highlight:: python

::

    from splinter import Browser
    executable_path = {'executable_path':'</path/to/phantomjs>'}

    browser = Browser('phantomjs', **executable_path)

API docs
--------

.. autoclass:: WebDriver
   :members:
   :inherited-members:
