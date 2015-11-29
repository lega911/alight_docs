Migration from 0.10 to 0.11
===========================

Controllers
```````````

.. code-block:: html
    :caption: html 0.10

    <div al-controller="main"></div>

.. code-block:: javascript
    :caption: js 0.10

    alight.controllers.main = function(scope) {};


.. code-block:: html
    :caption: html 0.11

    <div ctrl-main></div>

.. code-block:: javascript
    :caption: js 0.11

    alight.ctrl.main = function(scope, cd) {};

.. code-block:: javascript
    :caption: with "isolated" scope 0.11

    alight.ctrl.main = {
        scope: true,
        link: function(scope, cd) {
            scope.$parent // parent scope
        }
    };


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
    :caption: directive in 0.11

    alight.directives.al.test = function(scope, cd, element, value, env) {};

.. code-block:: javascript
    :caption: directive 0.11

    alight.directives.al.test = {
        scope: true,  // it make a new clean scope (object)
        ChangeDetector: true // true / 'root'
        link: function(scope, cd, element, value, env) {}
    }

Scope
`````

Scope - it was a mix of change detector and user's data, in v0.11 Scope was devided to ChangeDetector and scope={} (user's data), it gives different advatages.

.. code-block:: javascript
    :caption: Scope 0.10

    scope = alight.Scope()
    scope.name = 'linux'

    scope.$watch('name', function(value) {    
    }, {
        init: true  // it calls the callback immediately
    })

    scope.$scan()
    scope.$destroy()

.. code-block:: javascript
    :caption: v0.11

    scope = {
        name: 'linux'
    }
    cd = alight.ChangeDetector scope
    // now cd.scope === scope

    cd.watch('name', function(value) {});
    // you don't need set 'init' anymore, the callback is executed on finish binding process, also you can call cd.scan() for this.

    cd.scan()
    cd.destroy()
