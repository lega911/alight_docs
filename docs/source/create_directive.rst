Create Directives
==================================

Directives should be placed in **alight.directives.prefix**, you can choose any prefix, for example al-text ( *alight.directives.al.text* ), bo-text ( *alight.directives.bo.text* ), also you can place your directives in *scope.$ns.directives* they will be private.

A hyphen should be changed to underscores, example: :code:`<input al-my-some-directive />` it will be in alight.directives.al. **mySomeDirective**

The prefixes are needed in order to be able to catch the lack of used directives. For example, if you use the directive "al-texta", but it does not exists (a mistake in the name or js-file isn't loaded), then aLight will throw an exception.

An example of directive **al-text**, the directive is called when the binding process comes to an DOM-element

.. code-block:: javascript
   :caption: Example of directive al-text

    alight.directives.al.text = function(scope, element, name, env) {
        // Track to the variable
        scope.$watch(name, function(text) {
            // set a text to the DOM-element
            $(element).text(value)
        });
    };

**Input arguments:**

* **scope** - current Scope
* **cd** - change detector
* **element** - element of DOM
* **name** - value of attribute
* **env** - access to different options

* env. **attrName** - name of attribute (directive)
* env. **attributes** - list of attributes
* env. **takeAttr(name, skip=true)** - take a value of the attribute, if skip=true then the attribute will skip a binding process, sample
* env. **skippedAttr()** - list of not active attributes
* env. **stopBinding** = false - stop binding for child elements
* env. **changeDetector** - access to ChangeDetector
* env. **parentChangeDetector** - access to parent ChangeDetector (if scope was changed)


Attributes of directive:
------------------------

* **priority** - you can set priority for a directive
* **template** - custom template
* **templateUrl** - link to template
* **scope** (false/true) - if it is true, there will be a new, empty scope
* **ChangeDetector** (false/true/'root') - create a new change detector
* **restrict** = 'A', can be 'AEM', 'A' matches attribute name, 'E' matches element name, 'M' matches class name
* **link** - the method is called after template, scope
* **init** - the method is called when the directive is made, before template, scope. You usually need **link** instead of it.
* **stopBinding** (false/true) - stop binding for child elements
* *anyAttr* - you can make a custom attribute, look. directive preprocessor

.. code-block:: javascript
   :caption: Directives with attributes

    alight.directives.al.stop = {
        priority: -10,
        template: '<b></b>',
        stopBinding: true,
        link: function(scope, element, name, env) {
        }
    };

If "stopBinding" is true, then the process of binding will skip child DOM-elements, it is necessary for the directives which are themselves controlled subsidiary of DOM, such as al-repeat, al-controller, al-include, al-stop, etc.

.. raw:: html
   :file: discus.html
