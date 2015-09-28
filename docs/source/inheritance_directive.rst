Inheritance of directives
======================

If you want make inheritance of a directive, you need call a parent directive after that you can replace methods of the directive. For example, **al-value** has a few methods:

* onDom - binding to DOM
* updateModel - updateing the model
* watchModel - $watch model
* updateDom - updateting DOM
* initDom - set first value to DOM, updateDom(init_value)
* start - It's called when the directive is ready

Make a directive al-value with deferred updating of model:

.. code-block:: javascript
   :caption: Inherit al-value

    alight.directives.al.valueDelay = function() {
        // create a parent directive
        var dir = alight.directives.al.value.apply(null, arguments);

        // save the old method for update the model
        var oldUpdate = dir.updateModel;
        var timer = null;
        
        // change the method
        dir.updateModel = function() {
            if(timer) clearTimeout(timer);
            timer = setTimeout(function() {
                timer = null;

                // call the default method for update the model
                oldUpdate();
            }, 500);
        }
        return dir;
    }

Examples of inheritance
----------------------

* al-value -> `al-value-delay <http://jsfiddle.net/lega911/u4WnM/>`_
* al-show -> `al-show-slow <http://jsfiddle.net/lega911/3cGDc/>`_
* al-repeat, `add "$even", "$odd" into the directive <http://jsfiddle.net/lega911/zR3as/>`_
* al-repeat, `change input expression <http://jsfiddle.net/lega911/rB7y2/>`_ my-repeat="list.foreach item"
* al-repeat, `change rendering <http://jsfiddle.net/lega911/U7XTL/>`_

.. raw:: html
   :file: discus.html
