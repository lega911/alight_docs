Base filters
============

data
----

* To convert the date to string
* Input argument: date

.. code-block:: html
    :caption: example

    <div>{{when | date:yyyy-mm-dd }}</div>

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

    <div al-repeat="it in list | slice:a"></div>
    <div al-repeat="it in list | slice:a,b"></div>

generator
---------

* The filter makes an array (for al-repeat)
* input arguments: numbers

.. code-block:: html
    :caption: example

    <div al-repeat="it in 10 | generator"></div>
    <div al-repeat="it in size | generator"></div>

`Example <http://jsfiddle.net/lega911/v2uf2/>`_

.. raw:: html
   :file: discus.html
