Text directives
===============

Overview
--------

An able to control a declarative data binding in the HTML

.. code-block:: html
    :caption: example how to use text directives

    <div al-app>
        counter {{#counter}}
    </div>

.. code-block:: javascript
   :caption: text directive counter

    alight.text.counter = function(callback, expression, scope) {
        var n = 0;
        setInterval(function(){
            n++;
            callback(n)     // set result
            scope.$scan()       // $digest
        }, 1000);
    }

Input arguments
---------------

* **callback**   - a function to set a value
* **expression** - expression of directive
* **scope**      - scope
* **env**        - extra functional
 * env. **finally** - a function to set the final value, after that $watch will be removed.
 * env. **setter** = callback
 * env. **setterRaw** = send value directly


Examples
--------

* `Information output delay <http://jsfiddle.net/lega911/Y6QA4/>`_
* `An counter <http://jsfiddle.net/lega911/es8ph/>`_
* `An counter with setterRaw <http://jsfiddle.net/lega911/nL8xqctv/>`_
* `Sample with bindonce <http://jsfiddle.net/lega911/Q4cnM/>`_

.. raw:: html
   :file: discus.html
