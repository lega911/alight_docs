Create filters
==============

Overview
--------

A filter should be placed in **alight.filters**, or in scope.$ns for private filters.

.. code-block:: javascript
    :caption: Example filter

    alight.filters.double = function(value, expression, scope) {
    	return value + expression + value
    }

`Example on jsfiddle <http://jsfiddle.net/lega911/chbysp0a/>`_

Input arguments
---------------

* expression - an input expression
* scope - scope

The filter should return a handler/function, one instance of filter.

.. raw:: html
   :file: discus.html
