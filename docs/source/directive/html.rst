al-html
======

Overview
--------

* it includes a block of html

.. code-block:: html
   :caption: examples

    <div al-html="model"></div>
    <div al-html:id="templateId"></div>
    <div al-html:url="link"></div>
    <div al-html:url.tpl="/tpls/{{link}}.html"></div>

    <!-- alias -->
    <div :html="model"></div>
    <div :html.id="templateId"></div>
    <div :html.url="link"></div>
    <div :html.url.tpl="/tpls/{{link}}.html"></div>

Modifiers
---------

 * <empty> - takes html from model
 * id - takes html from a element by id
 * url - loads html from server
 * scope - makes a local variable for the template
 * tpl - the input variable is {{template}}
 * literal - the input variable is text/result
 * inline - takes html from innerHTML of current element
 * <custom> - you can make custom modifier (e.g. markdown, nobind...)

Examples
--------

 * al-html="model" - takes html from a value of the model
 * al-html:id="template" - takes html from element by id, id is taken from variable template
 * al-html:id.literal="templateId" - takes html from element where id = "templateId"
 * al-html:url="link" - loads html from a server, the url of templates is taken from variable "link"
 * al-html:url.literal="/tpls/file.html" - loads html from a server, url = "/tpls/file.html"
 * al-html:url.tpl="/tpls/{{name}}.html" - loads html from a server, url depends on variable "name"
 * al-html:inline="model" - takes html from current element and saves it to variable "model"
 * al-html:id.scope="templateId:inputVariable" - takes html element by id, makes a local variable "outer" for the template, and binds inputVariable: childScope.outer=scope.inputVariable

Examples
--------

* `Modifier "inline" displays a tree <http://jsfiddle.net/lega911/qbw5uhw3/>`_
* `Custom modifier "markdown" <http://jsfiddle.net/lega911/n67w47k8/>`_

.. raw:: html
   :file: ../discus.html
