Create filters
==============

Overview
--------

A filter can be placed in **scope** or in **alight.filters**, you can return Promise for deferred call.

.. code-block:: javascript
    :caption: Example filter

    alight.filters.wrap = function(value, text) {
        return text + value + text
    }

`Example on jsfiddle <https://jsfiddle.net/lega911/4wLwx1n3/>`_

Input arguments
---------------

* expression - an input expression
* scope - scope

The filter should return a handler/function, one instance of filter.

.. raw:: html
   :file: discus.html
