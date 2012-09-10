## Error Log

The Error Log is the place to track down syntax and parser errors that may cause an application or webpage to behave unexpectedly.

Click on the Errors icon in the application toolbar to access the Error Log. The number of errors for the current debugging context is conveniently displayed in the icon itself.

![Opera Dragonfly Error Log](img/error-all.jpg)

###Filter

To search through all errors on a page, use the Filter control on the Error Log toolbar.

![Opera Dragonfly Error Log filter function, showing only errors containing 'function'](img/error-filter.jpg)

###Tabs

By default, the All tab will be selected, showing every type of error for the current page. Depending on the types of error encountered on a page, more specific tabs will be displayed in addition to All. Errors can be filtered by choosing a more specific tab, for example the CSS tab.

Error messages can be opened one by one by clicking on them, or globally by clicking the Expand All icon in the Error Log toolbar.

![Expanded Error Log messages](img/error-expand-all.jpg)

###Error types

There are two error types displayed in the Error Log:

  * Error: An example would be a syntax error or an uncaught exception.
  * Information: This provides information, such as for an unknown property or value.
  
In the All tab view, each error is represented by its resource type icon whereas in more specific error tabs its icon represents the error type.

For CSS and JavaScript errors, clicking on the URL of the file in the expanded view will open the style sheet or script as a new tab in the Resource Inspector.

###CSS Filters

Custom CSS filters can be defined in the Error Log settings tab to remove certain types of errors from the All and CSS tabs of the Error Log. Comma-separated filters will be matched and ignored. For example, a filter such as `_padding` will force the Error log to ignore the IE6 underscore hack for padding properties.

![The filter in Opera Dragonfly's Preferences > Error Log for removing known CSS errors](img/error-css-filter.jpg)

###Clearing the Error Log

The Error Log can be cleared by clicking the trashcan icon in the toolbar or the "Clear all errors" context-menu item. Note that clicking the trashcan icon only clears visible errors, however. For example, if the current Error Log is filtered to show <code>-webkit-</code> CSS errors and the trashcan is clicked, as soon as the filter is cleared the remaining page errors are displayed.