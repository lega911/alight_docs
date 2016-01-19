Async filters
==============

Overview
--------

Async filters let you transform data in async mode, a filter should be placed in **alight.filters** or in scope.$ns for private filters.

Input arguments
---------------

* expression - an input expression
* scope - scope
* env - extra functional
* env.setValue(value) - set value of filter

.. code-block:: javascript
    :caption: Example of async filter

    alight.filters.asyncFilter = function(expression, scope, env) {};
    alight.filters.asyncFilter.prototype = {
        watchMode: 'deep',
        onChange: function(value) {},
        onStop: function() {}
    }

* watchMode, you can set 'simple'/'array'/'deep', if you need to change a watch mode for the input
* onChange - it's executed on every change of input
* onStop - it's executed when a watch object was removed

.. code-block:: javascript
    :caption: Example of async filter

    alight.filters.trottle = function(delay, scope, env) {
        delay = Number(delay);
        var to;
        this.onChange = function(value) {
            if(to) clearTimeout(to);
            to = setTimeout(function() {
                to = null;
                env.setValue(value);
                scope.$scan();
            }, delay);
        }
    }
    alight.filters.trottle.prototype.watchMode = 'simple';

.. code-block:: javascript
    :caption: Example 2 of async filter

    alight.filters.trottle = function(delay, scope, env) {
      this.delay = Number(delay);
      this.scope = scope;
    };

    alight.filters.trottle.prototype.onChange = function(value) {
        var that = this;
        if(that.to) clearTimeout(that.to);

        that.to = setTimeout(function() {
            that.setValue(value);
            that.scope.$scan();
        }, that.delay);
    }


.. code-block:: javascript
    :caption: Example in TypeScript

    class Trottle {
        constructor(delay, scope, env) {
            this.delay = Number(delay);
            this.scope = scope;
        }

        onChange(value) {
            if(this.to) clearTimeout(this.to);

            this.to = setTimeout( () => {
                this.setValue(value);
                this.scope.$scan();
            }, this.delay);
        }
    }

    alight.filters.trottle = Trottle;

.. code-block:: javascript
    :caption: Example in CoffeeScript

    class Trottle
        constructor: (@delay, @scope) ->

        onChange: (value) ->
            if this.to
                clearTimeout this.to

            this.to = setTimeout () =>
                this.setValue value
                this.scope.$scan()
            , this.delay

    alight.filters.trottle = Trottle

Examples
--------

* `Example trottle <http://jsfiddle.net/lega911/ktpoofcp/>`_
* `Example trottle, TypeScript <http://jsfiddle.net/lega911/Lkv0t80v/>`_
* `Example trottle, CoffeeScript <http://jsfiddle.net/lega911/tzt2r1na/>`_
* `Example with loading from server <http://plnkr.co/edit/JlHJijtwhZPUASsf2rNk?p=preview>`_

.. raw:: html
   :file: discus.html
