Component
=========

* Component is an isolated part of application, it has own change detector.
* Component has an isolated scope.
* Defined properties (:rating, :max in example below) are transferred to scope of component.
* You can choose a template returning template/templateId/templateUrl.
* Events onStart and onDestroy.
* If you use a prefix for name, then it throw error if a component doesn't exist (e.g. al-component).
* You can expose api from component
* Type of watchers for props: copy, array, deep and true (or empty).

.. code-block:: javascript
    :caption: Syntax

    alight.component('rating', (scope, element, env) => {
      return {
        template,
        templateId,
        templateUrl,
        props,
        onStart,
        onDestroy,
        api
      };
    })

.. code-block:: html
    :caption: Example of componenet

    <rating :rating="rating" :max="max" @change="rating=$value"></rating>

.. code-block:: javascript
    :caption: Example of componenet

    alight.component('rating', (scope, element, env) => {
      scope.change = (value) => scope.$dispatch('change', value)
        return {template: `<ul class="rating"><li al-repeat="_ in max" al-class="filled: $index<rating" @click="change($index+1)">\u2605</li></ul>`};
    })


If you want to define callback on property change or change type of observing of a property, you can do this in "props"

.. code-block:: javascript
    :caption: Configuring properties

    alight.component('somecomponent', (scope, element, env) => {
      return {
        props: {
            prop0: function(value) {},
            prop1: {
                watchMode: 'array'
            },
            prop2: {
                watchMode: 'deep',
                onChange: function(value) {}
            }
        }
      };
    })

.. code-block:: javascript
    :caption: Props as list

    alight.component('somecomponent', (scope, element, env) => {
      return {
        props: ['prop1', 'prop2']
      };
    })


`Example on jsfiddle <http://jsfiddle.net/lega911/vyoq12hj/>`_

.. raw:: html
   :file: discus.html
