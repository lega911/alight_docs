al-stop
=======

Overview
--------

* Stop bind process for the element
* Input argument: no

.. code-block:: html
    :caption: Example

    <div al-init="title='hello'">
        <span>{{title}}</span>
        <span al-stop>{{title}}</span>
    </div>

.. code-block:: html
    :caption: Result

    <div al-app al-init="title='hello'">
        <span>{{title}}</span>
        <span al-stop>{{title}}</span>
    </div>

.. raw:: html
   :file: ../discus.html
