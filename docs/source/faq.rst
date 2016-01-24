FAQ
==================

.. toctree::
   :maxdepth: 1

   faq/take_a_scope

* `How to call Alert from al-click <http://jsfiddle.net/lega911/Lv0g4anm/>`_
* Where can I take a debug version
    `Here <https://github.com/lega911/alight>`_ you can get release and debug of any version, also you can use bower: :code:`bower install alight`
* Where is $http service
    Angular Light doesn't have it, you can use jQuery.ajax or anyone that you usually use.
    But there is :code:`alight.f$.ajax` for inner purpose.
* Angular Light updates a whole DOM or it tracks changes and update only changed elements?
    Only changed elements.
* I need Angular Light runs my function when a bindings process will finish.
    You can observe it :code:`scope.$scan("$finishBinding", callback)`
* Is it possible to pass jquery $element to function from al-click?
    You can use $event that contains element, al-click="someFunc($event)"
* How can I use al-repeat not as attribute, but as a comment?
    al-repeat supports comment binding, `example <http://jsfiddle.net/lega911/mdt498e8/>`_
* Why al-show with an empty array doesn't hide my element: :code:`al-show="model.array"`?
    Because there is javascript and !!model.array always give you true, you can use :code:`al-show="model.array.length"`
* Where is "$odd, $even, $first, $last, $rest" for al-repeat?
    You can append any attributes, `example how to append $odd $even <http://jsfiddle.net/lega911/zR3as/>`_
* How to sort an array?
    `Manual sort <http://jsfiddle.net/lega911/81dqhL70/>`_
    `Filter orderBy <http://jsfiddle.net/lega911/q7jq1rwv/>`_
    `Sort props of an object <http://jsfiddle.net/lega911/nnk02xpy/>`_
    `Call a method <http://jsfiddle.net/lega911/msaLght8/>`_
* Can I rename directives?
    Yes, :code:`alight.directives.al.myKeypress = alight.directives.al.keypress`
* How to call my function when Scope.$scan finish digets process?
    You can pass your function as callback :code:`Scope.$scan(callback)`
* How to redraw bind-once?
    `Example <http://jsfiddle.net/lega911/wRA7L/>`_
* Where is DI?
    Angular Light doesn't have it, but you can make it for yourself, `example <http://plnkr.co/edit/WzkM0WLSBRYDmLxVUpJ8?p=preview>`_
* Why al-repeat displays not all items?
    Probably a input list contains doubles, in this case you should declare ID - using **track by**

    .. code-block:: html

        <div al-repeat="item in list track by $index">

    .. code-block:: html

        <div al-repeat="item in list track by items.id">

    Look at `al-repeat <directive/al-repeat.html>`_



.. raw:: html
   :file: discus.html
