Directive preprocessor
======================

Directive preprocessor lets you control process of creating directives. You can make custom attributes and make different transformations.

Objects:

* **alight.directivePreprocessor** - a default preprocessor, you can change it
* **alight.directivePreprocessor.ext** - a  list of handlers, you can append/remove them

.. code-block:: javascript
    :caption: Example how to create attribute 'bold'

    alight.directivePreprocessor.ext.splice(1, 0, {
        code: 'bold',  // not necessary
        fn: function() {
            if(this.directive.bold) this.element.innerHTML = '<b>' + this.element.innerHTML + '</b>'
        }
    })

.. code-block:: javascript
    :caption: How ot use it

    alight.directives.al.example = {
        bold: true
    }

* `Example on plunkr <http://plnkr.co/edit/XxDimA?p=preview>`_
* Article [ru]: `«Ленивое» подключение директив и препроцессор <http://habrahabr.ru/post/212301/>`_

.. raw:: html
   :file: discus.html
