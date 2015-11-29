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

alight.bootstrap(option)
`````````````````````````
It lets you a few ways to bind DOM, `read more <./bootstrap.html>`_

alight.bind(ChangeDetector, element, option)
````````````````````````````````````````````
Bind a change detector to the DOM element, alias **alight.applyBindings**

* ChangeDetector - an instance of ChangeDetector
* element - DOM element
* config.skip_top = false - Skip binding the top DOM element
* config.skip_attr = ['al-repeat', 'al-app'] - Skip attributes for a binding, for the top element

.. code-block:: javascript

    var cd = alight.ChangeDetector();
    var element = document.body;
    alight.bind(cd, element);


alight.ChangeDetector([scope])
``````````````
Create a new change detector, `read more <./change_detector.html>`_

alight.ctrl
``````````````````
Dictionary of controllers, alias for **alight.directives.ctrl**

alight.filters
``````````````
Dictionary of filters

alight.directives
`````````````````
Dictionary of directives, short alias **alight.d**

alight.text
```````````
Collection of text directives

alight.hook
```````````
Different hooks

alight.nextTick(callback)
`````````````````````````
Execute the function on next tick

.. raw:: html
   :file: discus.html
