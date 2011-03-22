#DOM Inspector

//TODO: check terminology. Fix header levels. Add screenshots. Change strings after string review

The DOM and Style Inspectors in Opera Dragonfly are accessible from the Documents panel in the application toolbar. The DOM Inspector is like View Source on steroids. While View Source shows the original document as it was written, the DOM Inspector shows the DOM tree as Opera sees it internally. This means that any DOM manipulation by scripts which have already been executed will show up in the DOM tree. Any malformed markup, such as misnested elements or missing mandatory close tags will also have been corrected according to Opera’s parsing algorithm. 

The Style Inspector is shown in the right hand panel. When a DOM element is selected, the styles corresponding to that node are shown.

##View options

//include a screen shot showing the two different view options

The DOM tree can be shown in one of two different modes. The default mode is similar to how markup is written using angle brackets, with the exception that nodes can be expanded and collapsed. The tree view (accessible from the context menu when right clicking on the DOM view) shows the DOM as a more classical tree. This view may be more familiar to DOM scripters, where for example text nodes are shown as a child node of type #text. 

A number of view options can be found in the settings, such as enabling and disabling the visibility of comment and white space nodes.

##Navigating the DOM panel

The main document is shown in the DOM source panel by default. Often this is the only DOM file, but if a document uses iframes, frames, or documents such as SVG files linked via the <code>object</code> element, they can be selected using the document selector. This can be found on the DOM toolbar to the left of the search button.

The DOM is shown collapsed by default. Clicking on the expander button to the left of the element will expand it to reveal its children. This can be achieved with the keyboard by pressing <kbd>Enter</kbd> when the expander has focus. Pressing <kbd>Shift</kbd>+<kbd>Enter</kbd> will expand the element and all of its children. It is often useful to expand the entire DOM at once. This can be achieved by pressing the <q>Expand the DOM tree</q> button in the DOM toolbar (first button on the left).

The DOM can be navigated using the arrow keys on the keyboard. Pressing the up and down arrows navigates between elements. The left and right arrow keys move between the individual tags, attributes and values of the element in focus. Pressing <kbd>Enter</kbd> will select the element, showing its associated styles in the right hand style panel, and highlighting it in the page. 

Any resource that is linked from the DOM can be opened in the Resource Inspector by @@@clicking on the link@@@@ (@@@ this might change. Too easy to open instead of edit right now@@@) or pressing <kbd>Enter</kbd> when the attribute value has focus. Examples of resources include CSS files linked via the <code>href</code> attribute of the <code>link</code> element, JavaScript files linked via the <code>src</code> attribute of the <code>script</code> element, and images linked via the <code>src</code> attribute of the <code>img</code> element, to name but a few.

##Highlighting and selecting elements

// show a screen shot of the element highlight

By default clicking on an element in the web page will select it in the DOM view, and highlight its dimensions, including the margin, border, padding and content boxes. Guidelines will also be shown to help judge the element’s alignment. Alternatively, an element can also be selected by clicking on it in the DOM view. The quickest way to select an element when Opera Dragonfly is not open is to right click on the element in the page and select <q>Inspect Element</q> from the context menu. This will open Opera Dragonfly and pre-select the element.

When element selection is turned on, the page’s default actions such as activating links or buttons are cancelled in favour of selecting the element in the DOM view. To restore the default action, element selection can be toggled off with the button highlighted in @@x.

It is also possible to disable the element highlight. This can be useful when it is important to see the original color of the selected element, such as when using the color picker.  The element highlight can be toggled off with the button highlighted in @@y.

The element highlight is fully customizable. The colors can be inverted using <kbd>Ctrl<kbd>+<kbd>I</kbd> (<kbd>⌘</kbd>+<kbd>I</kbd>) when the Opera Dragonfly window has focus. Individual components of the highlight can be enable or disabled as well as given a custom color in the Element highlight section of the Documents tab in Settings. 

It is sometimes useful to highlight multiple elements, such as when testing if elements line up correctly. This can be achieved in Opera Dragonfly by selecting @@<q>Keep elements highlighted</q> from the DOM panel context menu. When this option is enabled Opera Dragonfly will highlight each element that is selected on the page. Disabling this will return to only highlighting the last element that is clicked on. //@@@ This is currently not working. DFL-1598

##Search

To search the DOM press the Search button or <kbd>Ctrl</kbd>+<kbd>F</kbd> (<kbd>⌘</kbd>+<kbd>Shift</kbd>+<kbd>F</kbd> @@not currently working on Mac@@. A search toolbar will appear similar to the one in the Opera browser. From here it is possible to enter a search term, and navigate between the results with either the forward and backwards buttons or the <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd> keys. This only searches the currently visible DOM, so it is worth expanding all elements before searching.

##Editing the DOM

There are two different modes in Opera Dragonfly for editing the DOM. All elements are editable, except <code>script</code> elements. Editing individual attributes or values can be achieved by double clicking on the attribute or value, which will cause it to enter editing mode.  Alternatively select <q>Edit attribute</q> or <q>Edit attribute value</q> from the context menu, or pressing <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) when the attribute or value has focus. Pressing <kbd>Enter</kbd> will commit any changes. Pressing <kbd>Esc</kbd> cancels editing.

To edit the entire element, including its children, double click on the start or end tag. This will cause Opera Dragonfly to go into block edit mode, which allows for free form editing. Alternatively select <q>Edit markup</q> from the context menu, or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) when the start or end tag has focus. As <kbd>Enter</kbd> enters a new line, submitting changes is achieved by pressing <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) or clicking outside of the edit field.

An additional attribute can be added to the element while in edit mode by tabbing to the end of the element. An edit field for a new attribute will be created when tabbing past the last attribute. A quicker alternative is to select <q>Add attribute</q> from the element’s context menu.

An element can be removed from the document by selecting <q>Remove node</q> from the element’s context menu. @@@@ how to delete using keyboard? @@@@

##Viewing styles

The styles associated with the currently selected DOM element can be found in the Styles panel. There are two main sections; computed style and styles. 

The computed style section lists all the properties that Opera supports in alphabetical order. Each property lists its computed value. This is the value that Opera stores internally after all the rules have been evaluated and values have been converted. Number values are converted to pixels (px) (@@@are all numbers converted to px or just most?) and color values are converted to hexadecimal notation (except values that have an alpha channel which are converted to RGBA). 

The styles section contains a list of CSS rules in order of selector specificity (most specific first). Invalid rules that Opera could not parse are dropped from the rules, and shorthands are expanded into their individual properties. Like computed styles, units are converted to the value Opera stores internally. Properties in a less specific rule that are overridden by the same property in a more specific rule displayed with a strike through to show they do not apply. Properties that have a color value (such as <code>color</code> or <code>background-color</code>) show a color swatch after the value. Clicking on this swatch opens the color picker, which can be used to adjust the color on the fly.

It is easy to forget what a property does, or what its values mean. In Opera Dragonfly the relevant spec is only a click away. Each property includes a link to its spec in its context menu. This will open in a new tab. 

##Editing styles

Editing styles works the same way as editing the DOM. Double clicking on a property enters editing mode. Alternatively, select <q>Edit declaration</q> from the context menu, or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>). The property name or property value will be highlighted when entering editing mode, depending on which one was clicked upon. All styles can be edited except computed styles and default values. Default values are highlighted slightly differently to show they can’t be edited. Pressing <kbd>Enter</kbd> will commit the change, while <kbd>Esc</kbd> cancels editing. Invalid edits are ignored and the property returns to its original value.

Adding a new property can be achieved by double clicking at the end of an existing property and pressing <kbd>Enter</kbd> or selecting <q>Add declaration</q> from the context menu. It is important to note that as the properties are ordered alphabetically, if the new property is valid it will be move into the correct alphabetical position. An invalid property is ignored.

Deleting a property can be achieved by entering edit mode, selecting the whole line and pressing <kbd>Delete</kbd>.  (@@@@NOTE: why is there no delete declaration here?) 

Instead of deleting a property it is often useful while debugging to temporarily disable it. This can be achieved by hovering over a property and unchecking the check box. This will grey out the property. Checking the box again will re-enable it.

A quick way to make an overridden property apply without disabling all the more specific rules is to edit the property and add <code>!important</code>. The use of <code>!important</code> is generally not recommended but it can be useful while debugging. This will of course not work if the more specific rules also use <code>!important</code>.

It is often useful to add new rules while debugging, especially when there are no rules that match the element of interest. These can be added in the <q>New style</q> section. Free form text can be entered in the text field as if entering the text in a regular style sheet. Clicking the <q>Apply</q> button submits the changes and inserts a new <code>style</style> element into the document. Each new rule is evaluated and if the properties are valid they are included in the styles section of the elements that match the rule. Although the page updates instantly after clicking Apply, if any rules match the currently selected element it will have to be selected again to update the style panel view. @@@can this be fixed? @@@

##Color picker

// screen shot

The color picker can be used to edit a color value by selecting the desired color visually, rather than typing the color value. Every property in the styles section which accepts a color value includes a color swatch. Clicking on this opens the color picker. 

Using the color picker will be familiar to anyone that has used similar tools in an image editor. The two color swatches in the upper right hand corner show the original color (left) and the adjusted color (right). Clicking the original color swatch will revert the updated color to the original. 

The color can be adjusted using either the RGB or HSV color models. Clicking on the radio button next to a color component will clamp the color slider to the selected component. For instance, which clicking on the Hue (H) component the color slider is clamped to the values 0–360 (red to red, via the entire hue spectrum). Moving the slider will adjust only that component. The color field to the left of the slider is clamped to the other two components. Selecting a color in the field will update these two components. It is possible to directly enter the color value in either RGB, HSV or hexadecimal in the appropriate text fields.

If the color value has an alpha channel (RGBA or HSLA), an opacity slider is also available. This adjusts the color between fully opaque and fully transparent. A black and white pattern is displayed behind the original and adjusted color swatches to help visualize how the color will look. 


##Filtering styles

As the number of properties can quickly get unwieldy, it is possible to filter them with the Filter field. Only properties that match the term entered are displayed. The filter applies to both the regular and computed styles.

##Layout panel

The Layout panel contains information related to the box model and element positioning. The metrics diagram visualizes the various boxes of the box model. Hovering over each box highlights that specific component in the web page or application. This can be very useful for understanding exactly how the box model is being applied on the page.

The parent offsets section shows a breadcrumb trail of the currently selected element’s parents. Clicking on a node selects that element.

The offset values section lists all the DOM properties useful for understanding how the object is positioned on the page, such as the offset, client, and scroll position and dimensions. 

##Properties panel

While the style panel is useful when laying out and styling the document, the properties panel is useful when manipulating the DOM using JavaScript. It can be used to inspect the state of each element in the DOM, or check which properties are available.

The properties panel lists all the properties (called attributes in the DOM specs) of the currently selected DOM node object, along with their value. If an property has a long value, it is truncated and can be expanded with the expander button. Properties which are objects are listed with its type, and can be expanded to show the properties it contains.  As with CSS properties, it is possible to access the spec for each property from the context menu.

DOM node objects inherit properties and functions from their parent objects. For example, a <code>p</code> element is represented in the DOM by a <code>HTMLParagraphElement</code> object, which inherits from <code>HTMLElementPrototype</code>, which in turn inherits from <code>ElementPrototype</code>, <code>NodePrototype</code> and finally the <code>Object</code> object. Each prototype that the currently selected DOM node object inherits from are listed along with their properties and functions. They can be expanded and inspected just like regular objects.

###Showing and hiding properties

It is possible to hide non-enumerable properties, and default values which are null or empty strings using the corresponding buttons on the properties toolbar.

