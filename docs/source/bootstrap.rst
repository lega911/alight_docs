alight.bootstrap
================

A few ways to bind DOM.

Binding to all elements with attribute [al-app]
```````````````````````````````````````````````
* alight.bootstrap()

Binding by selector
```````````````````
* alight.bootstrap('#someId')
* alight.bootstrap('#someId', scope)

Binding to element
``````````````````
* alight.bootstrap(element)
* alight.bootstrap(element, scope)

Binding to array of elements
````````````````````````````
* alight.bootstrap([element1, element2, element3])
* alight.bootstrap([element1, element2, element3], scope)

**Note:** If you provide **scope**, then all elements will be binded to this scope, otherwise every dom will have own scope.

Example
```````

.. code-block:: javascript
   :caption: Example of bootstrap

    alight.bootstrap('#app', {
        name: 'world',
        click: function() {
            this.name = 'user'
        }
    });

.. code-block:: html
    <div id="app">
        Hello {{name}}!
        <button al-click="click()">Click</button>
    </div>
