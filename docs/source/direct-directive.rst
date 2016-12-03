
Direct directive
================

It lets you call js function with ability of a directive. Syntax: ``function-name!="arguments"``
A function can be global (optional) or in scope. You can pass arguments, also available builtins arguments: ``this (scope), $element, $env``.
By default a function receives scope, element, value, env.

.. code-block:: xml
    :caption: Example

    <p main-app!></p>
    <p some-func!="this, $element, 123"></p>


.. code-block:: javascript
    :caption: js part

    function mainApp(data, element, value, env) {
        data.someFunc = function(data, element, value) {        
        }
    }


`Example on jsfiddle <https://jsfiddle.net/lega911/10m4a8er/>`_
