Migration from 0.10 to 0.12
===========================

Controllers
```````````

.. code-block:: html
    :caption: html 0.10

    <div al-controller="main"></div>


.. code-block:: html
    :caption: html 0.12

    <div al-ctrl="main"></div>


Directives
``````````
.. code-block:: javascript
    :caption: directive in 0.10

    alight.directives.al.test = function(element, value, scope, env) {};

.. code-block:: javascript
    :caption: directive in 0.10

    alight.directives.al.test = {
        scope: true,  // true / 'isolate' / 'root'
        link: function(element, value, scope, env) {}
    }


.. code-block:: javascript
    :caption: directive in 0.12

    alight.directives.al.test = function(scope, element, value, env) {};

.. code-block:: javascript
    :caption: directive 0.12

    alight.directives.al.test = {
        scope: true,  // it make a new clean scope (object)
        link: function(scope, element, value, env) {}
    }
