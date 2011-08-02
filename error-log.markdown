## Error Log

The Error Log is the place to track down syntax and parser errors that may cause an application or webpage to behave unexpectedly.

Click on the Errors icon in the application toolbar to access the Error Log. The number of errors for the current debugging context is conveniently displayed in the icon itself.

![Opera Dragonfly Error Log](img/error-whole.png)

###Search

To search through all errors on a page, use the Filter control on the Error Log toolbar.

![Opera Dragonfly Error Log search](img/error-filter.png)

###Tabs

By default, the All tab will be selected, showing every type of error for the current page. Errors can be filtered by choosing a more specific tab such as the CSS tab.

Error messages can be opened one by one by clicking on them, or globally by clicking the Expand All icon in the Error Log toolbar.

![Expanded Error Log messages](img/error-detail.png)

###Error types

There are two error types displayed in the Error Log:

  * Error: An example would be a syntax error or an uncaught exception.
  * Information: This provides information, such as for an unknown property or value.

For CSS and JavaScript errors, clicking on the URL of the file in the expanded view will open the style sheet or script as a new tab in the Resource Inspector.

###CSS Filters

Custom CSS filters can be defined in the Error Log settings tab to remove certain types of errors from the All and CSS tabs of the Error Log. Comma-separated filters will be matched and ignored. For example, a filter such as `_padding` will force the Error log to ignore the IE6 underscore hack for padding properties.

![Filter for removing known CSS errors](img/error-css-filter.png)

###Clearing the Error Log

The Error Log is cleared by clicking the trashcan icon in the toolbar.