Scope
-----

Scope.$watch(name, callback, option)
````````````````````````````````````
Set the tracking variable. Also you can track system events, it returns object with method stop()

**Name:**

* **<expression>** - Expression/model
* **<a function>** - Track the result of the function, the function are called every iteration of $scan.
* **"$destroy"** - Track a destroying scope
* **"$any"** - Track a modifying any object
* **"$finishScan"** - a callback is executed as soon as $scan finish work
* **"$finishBinding"** - the callback is called when a binding process finishes, `sample <http://jsfiddle.net/lega911/4H86x/>`_
* **"$finishScanOnce"**

**Option:**

* **option** = true or **option.isArray** = true - watch an array
* **option.init** = true - Execute *callback*
* **option.readOnly** = true - You can use it if the *callback* doesn't modify the scope. (an optimization option).
* **option.deep** = true - a deep comparison for the object.
* **option.isArray**
* **option.OneTime**
* **option.onStop**

*Optimization tip*: If *callback* returns '$scanNoChanges' then $scan will not run extra-loop (like readonly watch)


Scope.$compile(expression, option)
``````````````````````````````````
Compile an expression

**option**:

* **option.input** - list of input arguments
* **option.no_return** - a function will not return any result (compile a statment)
* **option.string** - result of method will convert to string

.. code-block:: javascript
   :caption: Example of $compile

    var scope = alight.Scope()
    var fn = scope.$compile('"hello " + title')
    scope.title = 'linux'
    fn() // return "hello linux"
    scope.title = 'macos'
    fn() // return "hello macos"

.. code-block:: javascript
   :caption: Example with input

    var fn = scope.$compile('title + v', { input:['v'] })
    fn(' X') // return "macos X"

.. code-block:: javascript
    :caption: Example with no_return

    var fn = scope.$compile('title = v', { input:['v'], no_return:true })
    fn('linux') // scope.title = "linux"


Scope.$eval(expression)
```````````````````````
Execute an expression

Scope.$watchText(tpl, callback)
```````````````````````````````
Track the template

Scope.$compileText(tpl)
```````````````````````
Compile the template.
Method is depricated (since v0.9)

.. code-block:: javascript
    :caption: Example with $complieText

    var scope = alight.Scope()
    var fn = scope.$compileText('Hello {{title}}!')
    scope.title = 'linux'
    fn() // return "Hello linux!"

Scope.$evalText(tpl)
````````````````````
Evalute the template.
Method is depricated (since v0.9)


Scope.$new(isolate)
```````````````````
Create a child Scope, if isolate == true, then child scope will not be inherited from parent scope, if isolate == 'root' then it will be separate root scope.

Scope.$destroy()
````````````````
Destroy the Scope.

Scope.$scan(callback or option)
````````````````````````````````
Start the search for changes

* **callback** - Method will be called when $scan finishes a work, even if $scan has already started from other a place.

* **option.callback** - see above.
* **option.top** - Choose the root scope for current scanning (depricated).
* **option.late** = *(true/false)* - If there is a few $scan commands, Angular Light will call only last one.

.. code-block:: javascript
    :caption: Example with $scan

    var scope = alight.Scope()
    scope.$watch('title', function(value) {
        console.log('title =', value)
    }) // make observing
    scope.title = 'new'
    scope.$scan()
    // print title = new
    scope.title = 'linux'
    scope.$scan()
    // print title = linux
    scope.$scan()
    // do nothing

Scope.$scanAsync(callback)
``````````````````````````
It the same as *Scope.$scan({late: true, callback: callback})*


Scope.$getValue(name)
`````````````````````
Take the value of the variable, also you can use Scope.$eval

Scope.$setValue(name, value)
````````````````````````````
Set the value of the variable

.. code-block:: javascript
    :caption: Example with $setValue

    scope.var = 1;
    scope.path.var = 2;
    scope.path[scope.key] = 3;

    // equal
    scope.$setValue('var', 1);
    scope.$setValue('path.var', 2);
    scope.$setValue('path[key]', 3);

.. raw:: html
   :file: discus.html
