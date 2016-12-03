
Alight in 7 steps
=================

1. Install
----------
    
    1. ``npm install alight``
    2. ``bower install alight``
    3. Download from `site <http://angularlight.org/>`_
    4. CDN `cdn.rawgit.com/alight.js <https://cdn.rawgit.com/lega911/alight/v0.12.30/alight.js>`_


2. Bind data to DOM/HTML
------------------------

There is a few ways to bind:

    1. Using alight(element, data), `example <https://jsfiddle.net/lega911/LqzyLavg/>`_
    2. Using jQuery: $(selector).alight() `example <https://jsfiddle.net/lega911/8v935hbr/>`_
    3. Using attribute al-app `example <https://jsfiddle.net/lega911/pa184es1/>`_
    4. `More ways to bind <binding_to_dom.html>`_


3. How to listen events
-----------------------

You can bind any events using syntax ``al-on.event.modifier="expression"`` or shorter version ``@event.modifier="expression"``

.. code-block:: xml
    :caption: Example

    <button al-on.click="onClick()"></button>
    <button @click="onClick()"></button>


.. code-block:: xml
    :caption: Also you can use different modifiers, example

    <input @keydown.left="goLeft()" />
    <div @mousemove.throttle-300="moveWithDelay()"></div>

More information and examples is `here <events.html>`_.


4. Set attributes
-----------------

You can change value of any attribute using ``al-attr.attrName.modifier="value"`` or shorter version ``:attrName.modifier="value"``

.. code-block:: xml
    :caption: Example

    <input al-attr.hidden="value" />
    <input :hidden="value" />
    <input al-attr.disabled="value" />
    <input :disabled="value" />
    <img al-attr.src="linkToImage" />
    <img :src="linkToImage" />


.. code-block:: xml
    :caption: Style and class

    <div :class.red="redDiv"></div>
    <div :style.border-color="color"></div>


.. code-block:: xml
    :caption: Expression as template

    <img al-attr.src.tpl="/server/images/{{id}}" />
    <img :src.tpl="/server/images/{{id}}" />


More information is `here <directive/attr.html>`_.


5. Two-way binding
------------------

Set and get value of an element, you can use directives:

    * `al-value <directive/al-value.html>`_
    * `al-checked <directive/al-value.html>`_
    * al-radio
    * al-focused
    * al-select

.. code-block:: xml
    :caption: Example

    <input type="text" al-value="title" /> {{title}}
    <input type="checkbox" al-checked="model" />


6. How to call function/code
----------------------------

    1. You can use directive **al-init**, to call JS* expression, e.g. ``al-init="count=7; foo(count);"``, `read more <directive/al-init.html>`_
    2. Call a function from HTML, `direct-directive <direct-directive.html>`_


7. Manipulate blocks
--------------------

    1. Add and remove html blocks, directives **al-if** and **al-ifnot**, `jsfiddle example <https://jsfiddle.net/lega911/urLtajbw/>`_, `example 2 <http://jsfiddle.net/lega911/9v2DY/>`_
    2. Repeat blocks: `al-repeat <directive/al-repeat.html>`_
    3. Insert or load custom HTML: `al-html <http://localhost:8000/directive/html.html>`_
    4. `Component <component.html>`_
