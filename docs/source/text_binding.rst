Text bindings
=============

It's a way to draw information to DOM:

.. code-block:: html

    <div>Hello {{name}}!</div>
    <a href="htp://example.com/{{link}}>link</a>

Also you can use method "bind once" for optimization, for that you should append "=" to begin of expression.

.. code-block:: html

    <div>Hello {{=name}}!</div>
    <a href="htp://example.com/{{=link}}>link</a>


Also you can use `one time binding <one_time_binding.html>`_

If you can't use tags ``{{ }}``, you can change this to ``{# #}``, ``{< >}``, ``## ##`` or something like this, length of tags should be equal 2 symbols:

.. code-block:: javascript

    alight.utilits.pars_start_tag = '{#';
    alight.utilits.pars_finish_tag = '#}';

For complex text bindings you can use `text directives <text_directive.html>`_

.. raw:: html
   :file: discus.html
