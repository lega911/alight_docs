Create filters
==============

Overview
--------

A filter should be placed in **alight.filters** (you can change path with *alight.getFilter*), or in scope.$ns for private filters.

.. code-block:: javascript
    :caption: Example filter

    alight.filters.mylimit = function(exp, scope) {
        var ce = scope.$compile(exp);       // compile the input expression
        return function(value) {            // return handler
            var limit = Number(ce() || 5);
            return value.slice(0, limit)
        }
    }

`Example on jsfiddle <http://jsfiddle.net/lega911/pTT5x/>`_

Input arguments
---------------

* expression - an input expression
* scope - current Scope

The filter should return a handler/function, one instance of filter.

alight.getFilter(name, scope, param)
------------------------------------

This function look for a necessary filter, you can change it, for example you can make own location for your filters.
