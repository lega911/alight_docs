Create Directives
==================================

Directives should be placed in **alight.directives.prefix**, you can choose any prefix, for example al-text ( *alight.directives.al.text* ), bo-text ( *alight.directives.bo.text* ), also you can place your directives in *scope.$ns.directives* they will be private.

A hyphen should be changed to underscores, example: :code:`<input al-my-some-directive />` it will be in alight.directives.al. **mySomeDirective**

The prefixes are needed in order to be able to catch the lack of used directives. For example, if you use the directive "al-texta", but it does not exists (a mistake in the name or js-file isn't loaded), then aLight will throw an exception.

An example of directive **al-text**, the directive is called when the binding process comes to an DOM-element

.. code-block:: javascript
   :caption: Example of directive al-text

    alight.directives.al.text = function(element, name, scope, env) {
        // a function to set a text to the DOM-element
        var setter = function(text) {
            $(element).text(value)
        }

        // Track to the variable
        scope.$watch(name, setter, {
            init: true  // Run the setter immediately
        });
    };

**Input arguments:**

* **element** - element of DOM
* **name** - value of attribute
* **scope** - current Scope
* **env** - access to different options

* env. **attrName** - name of attribute (directive)
* env. **attributes** - list of attributes
* env. **takeAttr(name, skip=true)** - take a value of the attribute, if skip=true then the attribute will skip a binding process, sample
* env. **skippedAttr()** - list of not active attributes.

Attributes of directive:
------------------------

* **priority** - you can set priority for a directive
* **template** - custom template
* **templateUrl** - link to template
* **scope** (true/'isolate'/'root') - to make a child scope, an isolated scope (with no inheritance), a separate root scope
* **restrict** = 'A', can be 'AEM', 'A' matches attribute name, 'E' matches element name, 'M' matches class name
* **init** - the method is called when the directive is made, before template, scope
* **link** - the method is called after template, scope
* *anyAttr* - you can make a custom attribute, look. directive preprocessor

.. code-block:: javascript
   :caption: Directives with attributes

    alight.directives.al.stop = {
        priority: -10,
        template: '<b></b>',
        scope: true,
        init: function(element, name, scope, env) {
            return {
                owner: true
            };
        },
        link: function(element, name, scope, env) {
        }
    };

If a directive returns the flag owner :code:`return { owner:true }`, then the process of binding will miss child DOM-elements, it is necessary for the directives which are themselves controlled subsidiary of DOM, such as al-repeat, al-controller, al-include, al-stop, etc.

.. raw:: html
   :file: discus.html
