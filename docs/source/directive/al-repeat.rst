al-repeat
=========

Overview
--------

* Directive for building lists.
* Input argument: specific kind of expression

.. code-block:: html
    :caption: Syntax

    <li al-repeat="i in 10"></li>
    <li al-repeat="item in list"></li>
    <li al-repeat="item in list | filter"></li>
    <li al-repeat="item in list | filter | filter"></li>
    <li al-repeat="item in list | filter track by $index"></li>
    <li al-repeat="item in list track by $id(item)"></li>
    <li al-repeat="item in list track by item.id"></li>
    <li al-repeat="item in list track by $index"></li>
    <li al-repeat="item in list" al-controller="Controller"></li>
    <li al-repeat="item in list | filter store to filteredList"></li>
    <li al-repeat="item in list | filter track by $index store to filteredList"></li>

.. code-block:: html
    :caption: Bind to comment

    <div>
      <!-- directive: al-repeat item in list-->
      <b>{{$index}}</b>
      <i>{{item.kind}}</i>
      {{item.name}}<br/>
      <!-- /directive: al-repeat -->
    </div>

.. code-block:: html
    :caption: Iteration over an object

    <div al-repeat="(key,value) in user">
    <div al-repeat="(key,value) in user orderBy:key,reverse">
    <div al-repeat="(key,value) in user | some_filter orderBy:'key',reverse">
    <div al-repeat="(key,value) in user | some_filter orderBy:'key',reverse store to filteredList">

Description of attributes
-------------------------

* item - a name of variable for storing an element of list in child scope
* list - a source list
* filter - filters for the data
* track by - choose way to bind elements of the list to scope
* store to - store the resulting list to the scope

Example
-------

.. code-block:: html
    :caption: Example

    <div al-init="friends = [{name:'John', age:25}, {name:'Mary', age:28}]">
      I have {{friends.length}} friends. They are:
      <ul>
        <li al-repeat="friend in friends">
          [{{$index + 1}}] {{friend.name}} who is {{friend.age}} years old.
        </li>
      </ul>
    </div>

.. code-block:: html
    :caption: Result

    <div al-app al-init="friends = [{name:'John', age:25}, {name:'Mary', age:28}]">
      I have {{friends.length}} friends. They are:
      <ul>
        <li al-repeat="friend in friends">
          [{{$index + 1}}] {{friend.name}} who is {{friend.age}} years old.
        </li>
      </ul>
    </div>

Examples
--------

* `Sample with a filter <http://jsfiddle.net/lega911/vyEcA/>`_
* `Sample with a generator <http://jsfiddle.net/lega911/v2uf2/>`_
* `Sample with "store to variable" <http://jsfiddle.net/lega911/FVDJj/>`_
* `Sample with animation <http://jsfiddle.net/lega911/A5Vsk/>`_
* `Comment binding <http://jsfiddle.net/lega911/mdt498e8/>`_
* `Iteration over an object <http://jsfiddle.net/lega911/nnk02xpy/>`_
* `Other examples <http://angularlight.org/doc/examples.html#search=al-repeat>`_

.. raw:: html
   :file: ../discus.html
