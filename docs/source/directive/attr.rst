al-attr
=======

A way to set value for attribute/propery of element


.. code-block:: xml
    :caption: Examples

    <input al-attr.hidden="value" />
    <input :hidden="value" />
    <input al-attr.disabled="value" />
    <input :disabled="value" />
    <img al-attr.src="linkToImage" />
    <img :src="linkToImage" />


.. code-block:: xml
    :caption: Expression as template

    <img al-attr.src.tpl="/server/images/{{id}}" />
    <img :src.tpl="/server/images/{{id}}" />


Other attributes/properties
`````````````````````````````

* :checked
* :readonly
* :value
* :selected
* :muted
* :disabled
* :hidden
* :style
* :focus
* :<any attribute>

`al-html/:html <html.html>`_


Examples
````````

* `Example for style <http://jsfiddle.net/lega911/vxhdcj3f/>`_
