Controllers
===========

Overview
--------

* You can invoke a controller using directive al-ctrl="controllerName", also you can declare a top controller in directive al-app="controllerName".
* Your controller can be a simple function or a class.
* Your controller should be placed in alight.ctrl.controllerName or in scope.$ns.ctrl for a private controller or in global window.

Controller as a function
------------------------

.. code-block:: html
    :caption: Example controller as function

    <div al-app="main">
        {{myVar}}
    </div>

.. code-block:: javascript
    :caption: Example controller as function

    alight.ctrl.main = function(scope) {
        scope.myVar = 123;
    }

.. code-block:: javascript
    :caption: Example controller as function

    function main(scope) {
        scope.myVar = 123;
    }

`Example on jsfiddle <http://jsfiddle.net/lega911/86zennmt/>`_

Controller as a class
---------------------

.. code-block:: html
    :caption: Example controller as a class

    <div al-app="main">
        <button al-click="click()">Click</button>
        {{name}}
    </div>

.. code-block:: javascript
    :caption: Example controller as a class

    function main() {
        this.name = 'linux';
    }
    main.prototype.click = function() {
        this.name += '!'
    }

`Example on jsfiddle <http://jsfiddle.net/lega911/3y0ckykh/>`_

.. code-block:: javascript
    :caption: Controller in TypeScript

    class main {
        constructor() {
            this.name = 'linux';
        }

        click(value) {
            this.name += '!'
        }
    }

.. code-block:: javascript
    :caption: Controller in CoffeeScript

    class main
        constructor: () ->
            @.name = 'linux'

        click: () ->
            @.name += '!'


.. raw:: html
   :file: discus.html
