Async filters
==============

Overview
--------

Async filters let you transform data in async mode, a filter should be placed in **alight.filters** or in scope.$ns for private filters.

.. code-block:: javascript
    :caption: Example of async filter

    alight.filters.trottle = function(delay, cd, env) {
        delay = Number(delay);
        var to;
        return {
            onChange: function(value) {
                if(to) clearTimeout(to);
                to = setTimeout(function() {
                    to = null;
                    env.setValue(value);
                    cd.scan();
                }, delay);
            }
        }
    }

Input arguments
---------------

* expression - an input expression
* cd - change detector
* env - extra functional
* env.setValue(value) - set value of filter

.. code-block:: javascript
    :caption: Example of async filter

    alight.filters.asyncFilter = function(expression, cd, env) {
        return {
            watchMode: 'deep',
            onChange: function(value) {},
            onStop: function() {}
        }
    }

* watchMode, you can set 'simple'/'array'/'deep', if you need to change a watch mode for the input
* onChange - it's executed on every change of input
* onStop - it's executed when a watch object was removed

Examples
--------

* `Example trottle <http://jsfiddle.net/lega911/fkresedc/>`_
* `Example with loading from server <http://plnkr.co/edit/1pdQniodIjtmSuiZHDWo?p=preview>`_

.. raw:: html
   :file: discus.html
