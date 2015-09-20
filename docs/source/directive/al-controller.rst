al-controller
=============

Overview
--------

* The directive makes child scope, then calls a controller, then aLight bind scope with DOM
* input argument (not necessary): name of controller

.. code-block:: html
   :caption: Examples

    <div al-controller="bookCtrl"></div>
    <div al-controller="bookCtrl as book"></div>

.. code-block:: javascript
   :caption: Examples

    function bookCtrl(scope) {
    }

also you can place the controller into **alight.controllers** or in Scope.$ns for private controllers

.. code-block:: javascript
   :caption: Examples

    alight.controllers.bookCtrl = function(scope) {
    }
