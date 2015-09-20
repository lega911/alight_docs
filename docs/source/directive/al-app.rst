al-app
======

Overview
--------

* Bind a part of DOM on start
* input argument (not necessary): #tag and/or a name of controller

.. code-block:: html
   :caption: Examples

    <div al-app></div>
    <div al-app="mainCtrl"></div>
    <div al-app="#tag"></div>
    <div al-app="#tag mainCtrl"></div>

A tag lets you using one scope for different parts of DOM, also a tag places a scope to **alight.apps.tagName**

Examples
--------

* `One tag for different DOM <http://jsfiddle.net/lega911/ozk1gytu/>`_
* `Using tag and access to scope from outside <http://jsfiddle.net/lega911/hSHKZ/>`_
