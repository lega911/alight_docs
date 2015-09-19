FAQ
==================

.. toctree::
   :maxdepth: 1

   faq/take_a_scope

* `How to call Alert from al-click <http://jsfiddle.net/lega911/Lv0g4anm/>`_
* `How to simplify $parent.$parent.$parent... <http://jsfiddle.net/lega911/85axyo00/>`_
* `An one scope for a few applications <http://jsfiddle.net/lega911/93Ahp/>`_
* Where can I take a debug version
    `Here <https://github.com/lega911/alight>`_ you can get release and debug of any version, also you can use bower: :code:`bower install alight`
* Where is $http service
    Angular Light doesn't have it, you can use jQuery.ajax or anyone that you usually use.
    But there is :code:`alight.f$.ajax` for inner purpose.
* Angular Light updates a whole DOM or it tracks changes and update only changed elements?
    Only changed elements.
* I need Angular Light runs my function when a bindings process will finish.
    You can observe it :code:`scope.$scan("$finishBinding", callback)`
* Is it possible to pass jquery $element to function from al-click? Something like al-click="someFunc($this)"
    No, but you can extend the directive, or make a thin directive for this, `example <http://jsfiddle.net/lega911/2n1q7yt0/>`_
* How can I use al-repeat not as attribute, but as a comment?
    al-repeat supports comment binding, `example <http://jsfiddle.net/lega911/mdt498e8/>`_
* Why al-show with an empty array doesn't hide my element: :code:`al-show="model.array"`?
    Because there is javascript and !!model.array always give you true, you can use :code:`al-show="model.array.length"`
* Where is "$odd, $even, $first, $last, $rest" for al-repeat?
    You can append any attributes, `example hot to append $odd $even <http://jsfiddle.net/lega911/zR3as/>`_
* How to sort an array?
    `Simple way <http://jsfiddle.net/lega911/81dqhL70/>`_
    `With filter <http://jsfiddle.net/lega911/yud5yfcf/>`_
    `Call a method <http://jsfiddle.net/lega911/msaLght8/>`_
* Where is al-select directive?
    `Here <http://angularlight.org/doc/examples.html#search=select>`_ a few examples with select control.
* Can I rename directives?
    Yes, :code:`alight.directives.al.myKeypress = alight.directives.al.keypress`
* How to call my function when Scope.$scan finish digets process?
    You can pass your function as callback :code:`Scope.$scan(callback)`
