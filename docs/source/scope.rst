Scope
-----
It lets you observe changes in your scope, it uses change detector.

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
* **"$onScanOnce"** - the callback is called in scan loop

**Callback:**

The callback is called with two parameters. The first parameter contains the object after it has been changed, the second parameter contains the object before it has been changed. If the watched variable is not initialized, the second parameter is undefined.

**Option:**

* **option** = true or **option.isArray** = true - watch an array
* **option.readOnly** = true - You can use it if the *callback* doesn't modify the scope. (an optimization option).
* **option.deep** = true - a deep comparison for the object.
* **option.isArray**
* **option.OneTime**
* **option.onStop**

*Optimization tip*: If *callback* returns '$scanNoChanges' then $scan will not run extra-loop (like readonly watch)


Scope.$watchGroup(expression, callback)
``````````````````````````````````

Watches a group of expressions.
There are two approaches which can be used:

1. It returns a group object. You need to manually add more watcher objects to the group (`Example <https://jsfiddle.net/lega911/8om4ur4f/>`_).
2. Use an array as expression and watch it's items (`Example <https://jsfiddle.net/lega911/8nvb24uy/>`_).

**expression**:

* array of <expressions> - items which will be watched

**callback**

* will be executed when any item of the watched group has been changed


Scope.$compile(expression, option)
``````````````````````````````````
Compile an expression

**option**:

* **option.input** - list of input arguments
* **option.no_return** - a function will not return any result (compile a statment)
* **option.string** - result of method will convert to string

.. code-block:: javascript
   :caption: Example of $compile

    var scope = alight.Scope();
    var fn = scope.$compile('"hello " + title')
    scope.title = 'linux'
    fn(scope) // return "hello linux"
    scope.title = 'macos'
    fn(scope) // return "hello macos"

.. code-block:: javascript
   :caption: Example with input

    var fn = scope.$compile('title + v', { input:['v'] })
    fn(scope, ' X') // return "macos X"

.. code-block:: javascript
    :caption: Example with no_return

    var fn = scope.$compile('title = v', { input:['v'], no_return:true })
    fn(scope, 'linux') // scope.title = "linux"


Scope.$eval(expression)
```````````````````````
Execute an expression

Scope.$watchText(tpl, callback)
```````````````````````````````
Track the template

Scope.$destroy()
````````````````
Destroy the Scope.

Scope.$scan(callback or option)
````````````````````````````````
Starts the search for changes, returns a watch statistic

* **callback** - Method will be called when $scan finishes a work, even if $scan has already started from other a place.

* **option.callback** - see above
* **option.skipWatch** - skip specific watch
* **option.late** = *(true/false)* - If there is a few $scan commands, Angular Light will call only last one.

.. code-block:: javascript
    :caption: Example with $scan

    var scope = alight.Scope();
    scope.$watch('title', function(value) {
        console.log('title =', value)
    }); // make observing
    scope.title = 'new'
    scope.$scan()
    // print title = new
    scope.title = 'linux'
    scope.$scan()
    // print title = linux
    scope.$scan()
    // do nothing


Scope.$getValue(name)
`````````````````````
Take the value of the variable, also you can use Scope.$eval

Scope.$setValue(name, value)
````````````````````````````
Set the value of the variable

.. code-block:: javascript
    :caption: Example with $setValue

    var scope = {}
    scope.var = 1;
    scope.path.var = 2;
    scope.path[scope.key] = 3;

    // equal
    var scope = alight.Scope();

    scope.setValue('var', 1);
    scope.setValue('path.var', 2);
    scope.setValue('path[key]', 3);

.. raw:: html
   :file: discus.html
