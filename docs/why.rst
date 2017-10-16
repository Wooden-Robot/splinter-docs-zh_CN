+++++++++++++++++
为何使用Splinter?
+++++++++++++++++

Splinter是现有浏览器之上抽象层自动化工具（如 `Selenium`_, `PhantomJS`_ 和 `zope.testbrowser`_ )。它具有 :doc:`高级API
</api/index>` ，这使得它很容易去编写Web应用程序的自动化测试。

例如, 用Splinter填写一个表单项::

    browser.fill('username', 'janedoe')

在Selenium中, 等效代码会是::

    elem = browser.find_element.by_name('username')
    elem.send_keys('janedoe')

因为Splinter是一个抽象化层面, 它支持多种抽象化后端。使用Splinter，您可以使用相同的测试代码进行基于浏览器的测试，使用Selenium作为后端，并使用zope.testbrowser作为后端进行“headless”测试（无GUI）。

Splinter 有 :doc:`Chrome </drivers/chrome>` 和 :doc:`Firefox
</drivers/firefox>` for  的浏览器测试驱动,还有 :doc:`zope.testbrowser
</drivers/zope.testbrowser>` 和 :doc:`PhantomJS </drivers/phantomjs>` 用于headless测试.


.. _Selenium: http://seleniumhq.org
.. _zope.testbrowser: https://launchpad.net/zope.testbrowser
.. _PhantomJS: http://phantomjs.org
