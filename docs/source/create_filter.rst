Create filters
==============

Overview
--------

A filter should be placed in **alight.filters** (you can change path with *alight.getFilter*), or in scope.$ns for private filters.

.. code-block:: javascript
    :caption: Example filter

    alight.filters.mylimit = function(value, name, scope) {
        return value.slice(0, scope.$getValue(name));
    }

`Example on jsfiddle <http://jsfiddle.net/lega911/pTT5x/>`_

Input arguments
---------------

* expression - an input expression
* scope - scope

The filter should return a handler/function, one instance of filter.

.. raw:: html
   :file: discus.html
