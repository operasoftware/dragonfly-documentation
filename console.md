#Introducing the Dragonfly Console

## Console API

Dragonfly 1.0 ships with support for the [Firebug Console API](http://getfirebug.com/wiki/index.php/Console_API) (but see DFL-1522, DFL-1535). What this means is that console-based javascript debugging is now interoperable with Firebug, the WebKit Inspector, and the IE Developer Tools.

###`console.log(obj [, obj, ...])` and `console.debug(obj [, obj, ...])`

The most basic method for logging to the Dragonfly console is `console.log()`. `console.debug()` logs to the console with the line number where the code was called from. (But see DFL-1542)

    (might this be better a screenshot?)
    console.log(myVar);
    console.debug(myVar);

Multiple values can be logged inline by passing them in as additional arguments.

    console.log( 9001, true, { hello: "world" } )

###`console.warn(obj [, obj, ...])`, `console.error(obj [, obj, ...])`, and `console.info(obj [, obj, ...])`

`console.warn()`, `console.error()`, and `console.info()` offer the same functionality as console.log(), but with added semantics and visual emphasis (if DFL-1535 gets fixed). Similar to `console.debug()`, these methods print a hyperlinked line number ( see DFL-1542) that corresponds to where in the source it was called from.

    [screenshot showing the color differences, some possible examples:]
    console.warn( document.getElementById('foo') == null );
    console.error( 'Session is secure: ' + false );
    console.info( userObject );

###`console.dir(obj)` and `console.dirxml(DOM node)`

The `console.dir()` method is useful when you need to inspect the properties of an object or DOM node. It will log all the properties and values of the object passed in as interactive, inspectable items.

`console.dirxml()` is useful to for logging the structural representation of a DOM element, logging the structure of the node similar to what is seen in the Document view. Clicking on the logged element highlights it in the main document.

//dirxml() -> CORE-35765

###`console.count([name])`

The `console.count()` method logs the number of times a line of code is executed. You can pass in an optional name to aid in readability.

    var obj = { a: "a", b: "b" }
    for (var keys in obj) console.count('keys');

###`console.group(name)`, `console.groupCollapsed(name)`, `console.groupEnd()`

To create a collapsible group for a set of logged values, use the `console.group()` and `console.groupCollapsed()` methods. Begin the group by calling `console.group()` or `console.groupCollapsed()`, providing a name as an argument. Anything logged before `console.groupEnd()` is included in the named group.

    console.group('name');
    console.log('stuff that belongs in the group')
    console.groupEnd();

###`console.trace()`

The `console.trace()` method prints a stack trace to the console. You can click on the functions and argument values and inspect those in the Script tab.

###`console.time(name)`, `console.timeEnd(name)`

`console.time()` and `console.timeEnd()` log execution time of a code block. The names passed into `console.time()` and `console.timeEnd()` must match.

    console.time('loop');
    var i = 10;
    while ( i-- ) console.log( i );
    console.timeEnd('loop');

###console.assert(expression)

`console.assert()` logs an exception if an expression evaluates to false.

    console.assert( !true );

(see CORE-35518)

## Command Line API