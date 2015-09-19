A few ways to bind a model to the DOM
=====================================

1. Manual binding, applyBindings
--------------------------------

.. code-block:: html
    :caption: html

    <div id="app">
        <input al-value="title" type="text" class="form-control" />
        <p>{{title}}</p>
    </div>

Make scope, then to bind it to the DOM with **alight.applyBindings**

.. code-block:: javascript
    :caption: code

    var tag = document.querySelector('#app');  // take the tag

    var scope = alight.Scope();  // make a Scope
    scope.title = 'Hello!';  // set init value

    alight.applyBindings(scope, tag);  // apply bindings

`Example on jsfiddle <http://jsfiddle.net/lega911/D9t5F/>`_

2. Auto binding, al-app
-----------------------

**alight.bootstrap** is called on start system, it takes each element with **al-app** and execute **alight.applyBindings**

.. code-block:: html
    :caption: html

    <div al-app al-init="title='Hello!'">
        <input al-value="title" type="text" class="form-control" />
        <p>{{title}}</p>
    </div>

`Example on jsfiddle <http://jsfiddle.net/lega911/ASqeG/>`_


3. Manual binding with alight.bootstrap
---------------------------------------

You can bind custom elements with **alight.bootstrap**

.. code-block:: html
    :caption: html

    <div id="app" al-init="title='Hello!'">
        <input al-value="title" type="text" class="form-control" />
        <p>{{title}}</p>
    </div>


.. code-block:: javascript
    :caption: javascript

    var tag = document.querySelector('#app');  // take the tag

    alight.bootstrap([tag]);  // bind to DOM

`Example on jsfiddle <http://jsfiddle.net/lega911/kDp6X/>`_


4. Deferred binding, alight.bootstrap
-------------------------------------

.. code-block:: html
    :caption: html

    <div al-app al-init="title='Hello!'">
        <input al-value="title" type="text" class="form-control" />
        <p>{{title}}</p>
    </div>

.. code-block:: javascript
    :caption: javascript

    alight.autostart = false;
    setTimeout(alight.bootstrap, 2000);


`Example on jsfiddle <http://jsfiddle.net/lega911/mstLm/>`_


5. To bind to element with no DOM
---------------------------------

.. code-block:: html
    :caption: html

    <div id="app"></div>

.. code-block:: javascript
    :caption: javascript

    var tag = document.createElement('div');  // make an element
    // set up template
    tag.innerHTML = '<input al-value="title" type="text" class="form-control" /><p>{{title}}</p>';
    var scope = alight.Scope();  // make a scope
    scope.title = 'Hello!';  // set init value

    alight.applyBindings(scope, tag);  // apply bindings

    document.querySelector('#app').appendChild(tag);  // append to DOM

`Example on jsfiddle <http://jsfiddle.net/lega911/4MKP5/>`_


6. Manual binding #2
--------------------

.. code-block:: html
    :caption: html

    <div id="app">
        <input al-value="data.name" type="text" />
        {{data.name}} <br/>
        <button al-click="click()">Set Hello</button>
    </div>

.. code-block:: javascript
    :caption: javascript

    alight.bootstrap({
        $el: '#app',
        data: {
            name: 'Some text'
        },
        click: function() {
            this.data.name = 'Hello'
        }
    });

`Example on jsfiddle <http://jsfiddle.net/lega911/x04sxwme/>`_
