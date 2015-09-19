One-time binding
================

Overview
--------

Waits when an expression has a value (a non-undefined value), then stops watching. You need append "::" in front of expression for using One-Time binding. It works with $watch, $watchText, directives and declarative bindings.

.. code-block:: html
    :caption: example

    <div class="red {{::class}}"> {{::text}} </div>
    <div al-show="::visible"></div>
    <li al-repeat="it in ::list">...</li>
    and so on

Examples
--------

* `Sample with declarative bindings <http://jsfiddle.net/lega911/Ugcp8/>`_
* `Sample with al-repeat <http://jsfiddle.net/lega911/MSMPX/>`_
