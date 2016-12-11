Base filters
============

date
----

* To convert the date to string
* Input argument: date

.. code-block:: html
    :caption: example

    <div>{{when | date 'yyyy-mm-dd' }}</div>

filter
------

* To filter the list
* Input argument: variable

`Example <http://jsfiddle.net/lega911/vyEcA/>`_

slice
-----

* To slice the list
* input arguments: numbers

.. code-block:: html
    :caption: example

    <div al-repeat="it in list | slice a"></div>
    <div al-repeat="it in list | slice a,b"></div>


toArray
---------

* converts an object to array (for al-repeat)
* input arguments: key, value

.. code-block:: html
    :caption: example

    <div al-repeat="item in object | toArray key,value track by key">

`Example <http://jsfiddle.net/lega911/nnk02xpy/>`_

orderBy
---------

* sorts an array by key (for al-repeat)
* input arguments: key, reverse

.. code-block:: html
    :caption: example

    <div al-repeat="item in array | orderBy key,reverse">

`Example <http://jsfiddle.net/lega911/nnk02xpy/>`_

throttle
---------

* makes delay for output, pattern *debounce*
* input arguments: delay

.. code-block:: html
    :caption: example

    <input al-value="link" type="text" />
    <p>{{link | throttle 300 | loadFromServer}}</p>

`Example <http://jsfiddle.net/lega911/8fnh56op/>`_

json
----

* display data in json style

.. code-block:: html
    :caption: example

    {{data.value | json}}
    {{this | json}}

storeTo
----

* store result value to scope

.. code-block:: html
    :caption: example

    {{data.value | modifier | storeTo key}}

.. raw:: html
   :file: discus.html
