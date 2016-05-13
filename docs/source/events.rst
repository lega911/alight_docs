Events
======

A way to bind events.

.. code-block:: xml
   :caption: Syntax

   <div al-on.eventname.modifier="expression"> </div>
   <div @eventname.modifier="expression"> </div>


Modifiers for keydown, keypress, keyup
``````````````````````````````````````

* Filter by extra key: alt, control, meta, shift
* Filter by keycode: enter, tab, delete, backspace, esc, space, up, down, left, right, <any number of key code>

Special modifiers for all events
````````````````````````````````
* stop - calls stopPropagation
* prevent - calls preventDefault
* nostop - voids stopPropagation for click, dblclick, submit
* noprevent - voids preventDefault for click, dblclick, submit
* noscan - voids $scan
* throttle-<number>
* debounce-<number>

Modificators "prevent" and "stop" are on by default for click, dblclick and submit.
Available arguments in expressions: **$event, $element, $value**

Examples
````````

* al-on.keyup="onKeyup($event)"
* al-on.keydown.tab="onTab()"
* @keyup="onKeyup($event)"
* @keyup="key=$event.keyCode"
* @keydown.tab="onTab()"
* @keydown.enter="onEnter($event)"
* @keydown.13="onEnter($event)"
* @keydown.13.prevent="onEnter($event)"
* @keydown.control.enter="onEnter($event)"
* @keydown.control.shift.enter="onEnter($event)"
* @input="value=$event.target.value"
* @submit="onSubmit()"
* @submit.noprevent="onSubmit()"
* @click="onClick($event)"
* @click.noprevent="onClick()"
* @click.noprevent.stop="onClick()"
* @mousemove.noscan="onMousemove($event)"
* @mousemove.throttle-300="onMousemove($event)"
* @mousemove.debounce-300="onMousemove($event)"

You can make aliases and filters for events
```````````````````````````````````````````

It lets you:

* bind a few events to one expression
* makes custom modifiers (filters)
* make aliases for events

.. code-block:: javascript
   :caption: A few ways to make aliases

    alight.hooks.events.modifier['enter'] = 'keydown blur';
    alight.hooks.events.modifier['enter'] = ['keydown', 'blur'];
    alight.hooks.events.modifier['enter'] = (event, env) => {}
    alight.hooks.events.modifier['enter'] = {
      event: 'keydown blur',  // can be omitted
      fn: (event, env) => {}  // can be omitted
    }
    alight.hooks.events.modifier['enter'] = {
      event: ['keydown', 'blur'],
      fn: (event, env) => {
        env.stop = true;  // stop the event
      }
    }

Examples
````````

* `Throttle and Debounce for event-input and mousemove <http://jsfiddle.net/lega911/q8bxL1w5/>`_
* `Custom modifier/alias <http://jsfiddle.net/lega911/14ynfvmh/>`_
