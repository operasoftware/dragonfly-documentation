##Console

The Console is a useful tool for evaluating JavaScript statements, inspecting and logging objects and properties, and even adding functionality to a page for quick debugging.

The Console can be accessed by pressing the button with the command prompt icon in the application toolbar, or selecting the Console tab. Alternately, a Console HUD can be accessed and dismissed using the <kbd>Esc</kbd> key, displaying over the bottom half of the Opera Dragonfly window, which can be made taller or shorter by dragging the top with the mouse.

![Opera Dragonfly Console HUD](img/console-hud.png)

### Multi-line Editing

It can be useful to enter commands that span longer than a single line. When in the console's multi-line editing mode you can enter a block of text as if you were using a text editor, i.e., arrow and tab keys will behave as expected. This is handy, for example, when testing out a JavaScript function where whitespace aids in readability.

To enter multi-line editing, press <kbd>Shift + Enter</kbd>; pressing <kbd>Shift + Enter</kbd> again will toggle single-line mode. Once a block of text has been entered, <kbd>Ctrl + Enter</kbd> will simultaneously exit multi-line mode and interpret the text.

![Opera Dragonfly Console Multi-line Editing](img/multiline.png)

### Console API

Opera Dragonfly ships with support for the [Console API](http://getfirebug.com/wiki/index.php/Console_API). Anything logged by `console` methods is visible in the Console.

####`console.log(obj [, obj, ...])` and `console.debug(obj [, obj, ...])`

The most basic method for logging to the Opera Dragonfly console is `console.log()`. `console.debug()` logs to the console with the line number from where the code was called.

    console.log(myVar);
    console.debug(myVar);

Multiple values can be logged inline by passing them in as additional arguments.

    console.log( 9001, true, { hello: "world" } )

####`console.warn(obj [, obj, ...])`, `console.error(obj [, obj, ...])`, and `console.info(obj [, obj, ...])`

The `console.warn()`, `console.error()`, and `console.info()` methods offer the same functionality as console.log(), but with added semantics and visual emphasis. Similar to `console.debug()`, these methods print a hyperlinked line number that corresponds to the point in the source from where it was called.

    console.warn( document.getElementById('foo') == null );
    console.error( 'Session is secure: ' + false );
    console.info( userObject );

####`console.dir(obj)` and `console.dirxml(DOM node)`

The `console.dir()` method is useful when you need to inspect the properties of an object or DOM node. It will log all the properties and values of the object passed in as interactive, inspectable items.

The `console.dirxml()` method is useful for logging the structural representation of a DOM element and logging the structure of the node, similarly to what is seen in the Document view. Clicking on the logged element highlights it in the main document.

####`console.count([name])`
The `console.count()` method logs the number of times a line of code is executed. It is possible to pass in an optional name to aid in readability.

    var obj = { a: "a", b: "b" }
    for (var keys in obj) console.count('keys');

####`console.group(name)`, `console.groupCollapsed(name)`, `console.groupEnd()`

To create a collapsible group for a set of logged values, use the `console.group()` and `console.groupCollapsed()` methods. Begin the group by calling `console.group()` or `console.groupCollapsed()`, providing a name as an argument. Anything logged before `console.groupEnd()` is included in the named group.

    console.group('name');
    console.log('stuff that belongs in the group')
    console.groupEnd();

####`console.trace()`

The `console.trace()` method prints a stack trace to the console. It is possible to click on the functions and argument values and inspect those in the Script tab.

####`console.time(name)`, `console.timeEnd(name)`

`console.time()` and `console.timeEnd()` log execution time of a code block. The names passed into `console.time()` and `console.timeEnd()` must match.

    console.time('loop');
    var i = 10;
    while ( i-- ) console.log( i );
    console.timeEnd('loop');

#### console.assert(expression)

`console.assert()` logs an exception if an expression evaluates to false.

    console.assert( !true );

### Command Line API

The following command line shortcuts are available in the Console:

<table>
  <tr>
    <th>Shortcut</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>$("id")</code></td>
    <td>A shortcut for document.getElementById(), returns a DOM element</td>
  </tr>
  <tr>
    <td><code>$$("css selector")</code></td>
    <td>A shortcut for document.querySelectorAll(), returns a NodeList</td>
  </tr>
  <tr>
    <td><code>$0</code></td>
    <td>Variable containing the most recently inspected object</td>
  </tr>
  <tr>
    <td><code>$1</code></td>
    <td>Variable containing the next most recently inspected object</td>
  </tr>
  <tr>
    <td><code>dir(object)</code></td>
    <td>A shortcut for `console.dir()`</td>
  </tr>
  <tr>
    <td><code>clear()</code></td>
    <td>Clears the console</td>
  </tr>
  <tr>
    <td><code>keys(object)</code></td>
    <td>Logs all the keys of an Array-like object, returns an Array</td>
  </tr>
  <tr>
    <td><code>values(object)</code></td>
    <td>Logs all the (key) values of an Array-like object, returns an Array</td>
  </tr>
  <tr>
    <td><code>//help()</code></td>
    <td>Lists the available commands for the command line</td>
  </tr>
  <tr>
    <td><code>//man()</code></td>
    <td>Lists the available commands for the command line</td>
  </tr>
  <tr>
    <td><code>//jquery()</code></td>
    <td>Injects the latest (minified) version of jQuery into the page</td>
  </tr>
</table>

### Keyboard Shortcuts

The following cross-platform, Bash-like keyboard shortcuts are available in the Console (note: <kbd>Ctrl</kbd> is used on Mac rather than <kbd>Cmd</kbd> to be consistent with how Bash on Mac works):

<table>
  <tr>
    <th>Shortcut</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><kbd>Shift + Enter</kbd></td>
    <td>Enters multi-line mode</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + Enter</kbd></td>
    <td>Exits multi-line mode, and evaluates the entered text.</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + l</kbd></td>
    <td>Clears the console</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + e</kbd></td>
    <td>Moves to the end of the line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + a</kbd></td>
    <td>Moves to the beginning of the line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + k</kbd></td>
    <td>Deletes text to end of line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + u</kbd></td>
    <td>Deletes text to the beginning of the line</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + w</kbd></td>
    <td>Deletes a word backwards</td>
  </tr>
  <tr>
    <td><kbd>Ctrl + y</kbd></td>
    <td>Pastes the content of the delete buffer; sets the buffer to whatever was last deleted by Ctrl-K,U, or W.</td>
  </tr>
</table>

In addition to the previous shortcuts, pressing <kbd>Tab</kbd> can be used to auto-complete an identifier (including the so-called native built-in objects, i.e., <code>Array</code> & <code>[]</code>, String, Number, etc.), or print out a list of possible matches.

![Tab completion](img/console-tab.png)