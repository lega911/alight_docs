A few ways to bind a model to the DOM
=====================================

1. Auto binding, al-app
-----------------------

**alight()** is called on start system, it takes each element with **al-app** and bind it.

.. code-block:: xml
    :caption: html

    <div al-app al-init="title='Hello!'">
        <input al-value="title" type="text" class="form-control" />
        <p>{{title}}</p>
    </div>


`Example on jsfiddle <http://jsfiddle.net/lega911/ASqeG/>`_


2. Manual binding with alight()
---------------------------------------

You can bind custom elements with **alight()**

.. code-block:: xml
    :caption: html

    <div id="app" al-init="title='Hello!'">
        <input al-value="title" type="text" class="form-control" />
        <p>{{title}}</p>
    </div>


.. code-block:: javascript
    :caption: javascript

    alight('#app');  // bind to DOM

`Example on jsfiddle <https://jsfiddle.net/lega911/yrpyL2cj/>`_


3. To bind to element with no DOM
---------------------------------

.. code-block:: xml
    :caption: html

    <div id="app"></div>

.. code-block:: javascript
    :caption: javascript

    var tag = document.createElement('div');  // element
    tag.innerHTML = '<input al-value="title" type="text" class="form-control" /><p>{{title}}</p>';  // template

    alight(tag, {title: 'Hello!'});  // binding

    document.querySelector('#app').appendChild(tag);  // append to DOM

`Example on jsfiddle <https://jsfiddle.net/lega911/c4dav854/>`_


4. Manual binding #2
--------------------


.. code-block:: xml
    :caption: html
    
    <div id="app">
        <input al-value="name" type="text" />
        {{name}} <br/>
        <button @click="click()">Set Hello</button>
    </div>


.. code-block:: javascript
    :caption: javascript

    var data = {
        name: 'Some text',
        click: function() {
            data.name = 'Hello';
        }
    };

    alight('#app', data);

`Example on jsfiddle <https://jsfiddle.net/lega911/ax4srp5k/>`_

.. raw:: html
   :file: discus.html
