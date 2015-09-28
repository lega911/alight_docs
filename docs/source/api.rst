API
=========================================

alight.debug
````````````
Turn on a logging debug information

* alight.debug.scan - logging scan operations
* alight.debug.directive - logging binding directives
* alight.debug.parser - logging parsing expressions
* alight.debug.watch - logging function $watch
* alight.debug.watchText - logging function $watchText

alight.autostart = false
````````````````````````
Don't call alight.bootstrap on start

alight.bootstrap(element)
`````````````````````````
Manual start applications, element - DOM element or array of elements. If element is undefined then Angular Light will start all al-app on the document. If alight.autostart = true, the method will be called after the DOM is ready

alight.applyBindings(scope, element, config)
````````````````````````````````````````````
Bind the scope to the DOM element

* scope - Scope object
* element - DOM element
* config.skip_top = false - Skip binding the top DOM element
* config.skip_attr = ['al-repeat', 'al-app'] - Skip attributes for a binding, for the top element

.. code-block:: javascript

    var scope = alight.Scope();
    var element = document.body;
    alight.applyBindings(scope, element);


alight.Scope()
``````````````
Create a (root) Scope

alight.controllers
``````````````````
Dictionary of controllers

alight.filters
``````````````
Dictionary of filters

alight.directives
`````````````````
Dictionary of directives

alight.nextTick(callback)
`````````````````````````
Execute the function on next tick

alight.getController(name, scope)
`````````````````````````````````
Take a controller by name. A controller can be located in alight.controllers, in global scope

.. raw:: html
   :file: discus.html
