##DOM Inspector

The DOM and Style Inspectors in Opera Dragonfly are accessible from the Documents panel in the application toolbar. The DOM Inspector is like View Source on steroids. While View Source shows the original document as it was written, the DOM Inspector shows the DOM tree as the Opera browser sees it internally. This means that any DOM manipulation by scripts that have already been executed will show up in the DOM tree. Any malformed markup, such as improperly nested elements or missing mandatory closing tags will also have been corrected according to Opera’s parsing algorithm. 

The Style Inspector is shown in the right-hand sub-panel. When a DOM element is selected, the styles corresponding to that node are shown.

<img src="img/dom-overview.png" alt="Overview of the DOM and Style Inspector UIs" />

###View options

The DOM tree can be shown in one of two different modes. The default mode is similar to how markup is written using angle brackets, with the exception that nodes can be expanded and collapsed. The tree view (accessible from the context menu when right clicking on the DOM view) shows the DOM as a more classical tree. This view may be more familiar to DOM scripters, where, for example, text nodes are shown as a child node of type #text. 

<img src="img/tree-view.png" alt="The DOM represented as a node tree" />

A number of view options can be found in the settings, such as enabling and disabling the visibility of comment and whitespace nodes.

###Navigating the DOM panel

The main document is shown in the DOM source sub-panel by default. Often this is the only DOM file, but if a document uses iframes, frames, or documents such as SVG files linked via the <code>object</code> element, they can be selected using the document selector. This can be found on the DOM toolbar to the left of the search button.

The DOM is shown collapsed by default. Clicking on the expander button to the left of the element will expand it to reveal its children and pseudo elements (if any). This can be achieved with the keyboard by pressing <kbd>Enter</kbd> when the expander has focus. Pressing <kbd>Shift</kbd>+<kbd>Enter</kbd> will expand the element and all of its children. It is often useful to expand the entire DOM at once. This can be achieved by pressing the <q>Expand the DOM tree</q> button in the DOM toolbar, which is the first button on the left.

The DOM can be navigated using the arrow keys on the keyboard. Pressing the up and down arrows navigates between elements. The left and right-arrow keys move between the individual tags, attributes and values of the element in focus. Pressing <kbd>Enter</kbd> will select the element, showing its associated styles in the right-hand style sub-panel and highlighting it in the page. 

Any resource that is linked from the DOM can be opened in the Resource Inspector by selecting <q>Show resource</q> from the context menu. Examples of resources include CSS files linked via the <code>href</code> attribute of the <code>link</code> element, JavaScript files linked via the <code>src</code> attribute of the <code>script</code> element, and images linked via the <code>src</code> attribute of the <code>img</code> element, to name but a few.

####Highlighting and selecting elements

Clicking on an element in the webpage will select it in the DOM view and highlight its dimensions, including the margin, border, padding and content boxes. Guidelines will also be shown to help judge the element’s alignment. Alternatively, an element can also be selected by clicking on it in the DOM view. The quickest way to select an element when Opera Dragonfly is not open is to right-click on the element in the page and select <q>Inspect Element</q> from the context menu. This will open Opera Dragonfly and pre-select the element.

When element selection is turned on, the page’s default actions such as activating links or buttons are canceled in favor of selecting the element in the DOM view. To restore the default action, element selection can be toggled off with the Select Element button.

It is also possible to disable the element highlight. This can be useful when it is important to see the original color of the selected element, such as when using the color picker.  The element highlight can be toggled off with the Highlight Element button.

The element highlight is fully customizable. The colors can be inverted using <kbd>Ctrl</kbd>+<kbd>I</kbd> (<kbd>⌘</kbd>+<kbd>I</kbd>) when the Opera Dragonfly window has focus. A custom color can be set in the Element highlight section of the Documents tab in Settings. 

<img src="img/inverted-highlight.png" alt="Multiple elements highlighted in the page" />

It is sometimes useful to highlight multiple elements, such as when testing whether elements line up correctly. This can be achieved in Opera Dragonfly by selecting <q>Keep elements highlighted</q> from the DOM sub-panel context menu. When this option is enabled Opera Dragonfly will highlight each element that is selected on the page. Disabling this will return to only highlighting the last element that is clicked.

<img src="img/element-highlight.png" alt="Multiple elements highlighted in the page" />


####Search

To search the DOM, switch to the Search panel or press <kbd>Ctrl</kbd>+<kbd>F</kbd> (<kbd>F3</kbd> or <kbd>fn</kbd>+<kbd>F3</kbd> for keyboards that apply a OS function to the function keys). From the Search panel it is possible to enter a search term, and navigate between the results with either the forward and back buttons or the <kbd>Enter</kbd> and <kbd>Shift</kbd>+<kbd>Enter</kbd> keys. A badge is shown in the search field to show the current match and total matches. All matches are shown as a list in the Search panel once the search query is submitted. Selecting a match will highlight it in the DOM source. There are a number of search options described below.

<img src="img/css-search.png" alt="Search options include search by CSS selector" />


#####Text search

The text search works somewhat differently than in Opera Dragonfly 1.0. In Opera Dragonfly 1.1 and above, the full DOM can be searched, including collapsed element nodes. The text search matches text within the <code>nodeName</code>, the attribute <code>name</code> and <code>value</code>, text nodes, and comments rather than freeform text across nodes. This means that searching for <code>&lt;div</code> will not match the <code>div</code> element start or end tag as the opening angled bracket is outside of the <code>nodeName</code>. Similarly <code>li id=</code> will not match an <code>li</code> element with the first attribute of <code>id</code> as the id attribute and li start tag span two different nodes.

##### RegExp search

The RegExp search allows for searching using JavaScript regular expressions. RegExp matches results in the same way as text search, rather than being a freeform search.

##### CSS selector search

The CSS selector search accepts a selector string, in much the same way as <code>querySelectorAll</code> from the <a href="http://www.w3.org/TR/selectors-api/#selector-string">Selectors API</a>. DOM elements that match the entered selector string are shown in the results. As well as for searching the DOM, this can be useful for quickly testing if a selector will match the required elements.

##### XPath expression search

The XPath expression search works the same way as the CSS selector search, except it shows which elements match the entered XPath expression.

##### Ignore case option

The ignore case checkbox can be enabled for text and RegExp searches. When enabled the search is case insensitive so for example a search for <q>div</q> will match no matter if <q>DIV</q> or <q>div</q> is used.

####Editing the DOM

There are two different modes in Opera Dragonfly for editing the DOM. All elements are editable, except <code>script</code> elements. Editing individual attributes or values can be achieved by double-clicking on the attribute or value, which will cause it to enter editing mode.  Alternatively, select <q>Edit attribute</q> or <q>Edit attribute value</q> from the context menu, or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) when the attribute or value has focus. Pressing <kbd>Enter</kbd> will commit any changes. Pressing <kbd>Esc</kbd> cancels editing.

To edit the entire element, including its children, double-click on the start or end tag. This will cause Opera Dragonfly to go into block edit mode, which allows for free-form editing. Alternatively, select <q>Edit markup</q> from the context menu, or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) when the start or end tag has focus. As <kbd>Enter</kbd> enters a new line, submitting changes is achieved by pressing <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>) or clicking outside of the edit field.

<img src="img/edit-markup.png" alt="Editing the DOM" />

An additional attribute can be added to the element while in edit mode by tabbing to the end of the element. An edit field for a new attribute will be created when tabbing past the last attribute. A quicker alternative is to select <q>Add attribute</q> from the element’s context menu.

An element can be removed from the document by selecting <q>Delete node</q> from the element’s context menu.

####Viewing pseudo elements

CSS pseudo elements are not actually part of the DOM, but they can be seen in the Opera Dragonfly DOM panel when a CSS selector defines one, so that the style declarations can be inspected. Pseudo elements are displayed as if they were an element with the tag name of the pseudo element in question proceeded by two colons. For example the ::first-letter pseudo element is shown as &lt;::first-letter/> before the first child of the element of which it applies. 

<img src="img/pseudo-elements" alt="viewing pseudo elements in the DOM" />

####Viewing styles

The styles associated with the currently selected DOM element can be found in the Styles sub-panel. There are two main sections; computed style and styles. 

The computed style section lists all the properties that the Opera browser supports in alphabetical order. Each property lists its computed value. This is the value that the Opera browser stores internally after all the rules have been evaluated, and values and units have been converted. For example, color values are converted to hexadecimal notation (except values that have an alpha channel, which are converted to <a href="http://www.w3.org/TR/css3-color/#rgba-color">RGBA</a>), and length values are converted to pixels (<code>px</code>).

The styles section contains a list of CSS rules in order of selector specificity, with the most specific first. Invalid rules that the Opera browser could not parse are dropped from the rules, and shorthands are expanded into their individual properties. As with computed styles, units are converted to the value the Opera browser stores internally. Properties in a less specific rule that are overridden by the same property in a more specific rule display with a strike-through to show they do not apply. Properties that have a color value (such as <code>color</code> or <code>background-color</code>) show a color swatch after the value. Clicking on this swatch opens the color picker, which can be used to adjust the color on the fly.

<img src="img/styles-panel.png" alt="The styles sub-panel" />

Links to the right of the selector show the file in which the CSS rule was defined. Clicking the link will open the file in the Resource Inspector and scroll to the correct line in the document. This will show the style sheet as it was written originally rather than the parsed styles shown in the Style Inspector.

It is easy to forget what a property does, or what its values mean. In Opera Dragonfly, the relevant spec is only a click away. Each property includes a link to its spec in its context menu. This will open in a new tab. 

##### Pseudo classes

Pseudo classes can also be seen in the styles section. Normally only rules that are currently active are shown. This makes it difficult to see styles that are only applied temporarily, such as active and hover styles. To make this easier, Opera Dragonfly provides a drop down button on the styles toolbar, which lists the pseudo classes and the selection pseudo element. If an option is enabled any rules with the matching pseudo class will be displayed in the Style Inspector as if it was currently active.

<img src="img/pseudo-classes" alt="viewing pseudo classes" />

##### SVG presentational attributes

SVG presentational attributes map directly to their equivalent CSS properties, but with a specificity of 0. To take advantage of Opera Dragonfly’s CSS editing and debugging features, and to keep all the styling information in one place, SVG presentational attributes are mapped to their CSS equivalent in the Style Inspector. All presentational attributes on an element are displayed in one rule block with <q>Presentational attributes</q> replacing the selector string. Do to the low specificity they will be shown at the very bottom of the list of rules. 

<img src="img/presentational attributes.png" alt="viewing presentational attributes in Style Inspector" />


####Editing styles

Editing styles works the same way as editing the DOM. Double-clicking on a property enters editing mode. Alternatively, select <q>Edit declaration</q> from the context menu, or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> (<kbd>⌘</kbd>+<kbd>Enter</kbd>). The property name or property value will be highlighted when entering editing mode, depending on which one was clicked upon. All styles can be edited except computed styles and default values. Default values are highlighted slightly differently to show they can’t be edited. Pressing <kbd>Enter</kbd> will commit the change, while <kbd>Esc</kbd> cancels editing. Invalid edits are ignored and the property returns to its original value.

Adding a new property can be achieved by double-clicking at the end of an existing property and pressing <kbd>Enter</kbd> or selecting <q>Add declaration</q> from the context menu. It is important to note that as the properties are ordered alphabetically, if the new property is valid it will be move into the correct alphabetical position. An invalid property is ignored.

Deleting a property can be achieved by entering edit mode, selecting the whole line and pressing <kbd>Delete</kbd>, or selecting <q>Delete declaration</q> from the context menu.

Instead of deleting a property it is often useful while debugging to temporarily disable it. This can be achieved by hovering over a property and unchecking the checkbox. This will grey out the property. Checking the box again will re-enable it.

<img src="img/disabled-declarations.png" alt="Disabling CSS properties" />

A quick way to make an overridden property apply without disabling all the more specific rules is to edit the property and add <code>!important</code>. The use of <code>!important</code> is generally not recommended for accessibility and maintainability reasons, but it can be useful while debugging. This will of course not work if the more specific rules also use <code>!important</code>.

It is often useful to add new rules while debugging, especially when there are no rules that match the element of interest. These can be added in the <q>New style</q> section. Free-form text can be entered in the text field as if entering the text in a regular style sheet. Clicking the <q>Apply</q> button submits the changes and inserts a new <code>style</code> element into the document. Each new rule is evaluated, and, if the properties are valid, they are included in the styles section of the elements that match the rule. Although the page updates instantly after clicking Apply, if any rules match the currently selected element it will have to be selected again to update the style sub-panel view.

<img src="img/add-rule.png" alt="Adding a new CSS rule" />

####Color picker

The color picker can be used to edit a color value by selecting the desired color visually, rather than typing the color value. Every property in the styles section that accepts a color value includes a color swatch. Clicking on this opens the color picker. 

<img src="img/color-picker.png" alt="Using the color picker" />

Using the color picker will be familiar to anyone who has used similar graphics-related tools. The two color swatches in the upper-right-hand corner show the original color (left) and the adjusted color (right). Clicking the original color swatch will revert the updated color to the original. 

The color can be adjusted using either the <a href="http://en.wikipedia.org/wiki/RGB_color_model">RGB</a> or <a href="http://en.wikipedia.org/wiki/HSL_and_HSV">HSV</a> color models. Clicking on the radio button next to a color component will clamp the color slider to the selected component. For instance, which clicking on the Hue (H) component, the color slider is clamped to the values 0–360 (red to red, via the entire hue spectrum). Moving the slider will adjust only that component. The color field to the left of the slider is clamped to the other two components. Selecting a color in the field will update these two components. It is possible to directly enter the color value in either RGB, HSV or hexadecimal in the appropriate text fields.

If the color value has an alpha channel (RGBA or HSLA), an opacity slider is also available. This adjusts the color between fully opaque and fully transparent. A black-and-white pattern is displayed behind the original and adjusted color swatches to help visualize how the color will look. 

A color palette is available at the bottom of the color picker. This contains all the colors stored from the Utilities color picker. The list of colors can be managed from the <q>color palette</q> sub-panel in Utilities. This can be useful for storing the colors defined in a company style guide for example.  

####Filtering styles

As the number of properties can quickly get unwieldy, it is possible to filter them with the Filter field. Only properties that match the term entered are displayed. The filter applies to both the regular and computed styles.

###Layout panel

The Layout sub-panel contains information related to the box model and element positioning. The metrics diagram provides a visualization of the various boxes of the box model. Hovering over each box highlights that specific component in the webpage or application. This can be very useful for understanding exactly how the box model is being rendered for those elements.

The <q>parent offsets</q> section shows a breadcrumb trail of the currently selected element’s parents. Clicking on a node selects that element.

<img src="img/layout-panel.png" alt="The layout sub-panel" />

The offset values section lists all the DOM properties useful for understanding how the object is positioned on the page, such as the offset, client, and scroll position and dimensions. 

###Properties panel

While the style sub-panel is useful when laying out and styling a document, the properties sub-panel is useful when manipulating the DOM using JavaScript. This panel can be used to inspect the state of each element in the DOM or to check which properties are available.

The properties sub-panel lists all the properties (called attributes in the DOM specs) of the currently selected DOM node object, along with their values. If a property has a long value, it is truncated and can be expanded with the expander button. Properties that are objects are listed with its type and can be expanded to show the properties the object contains.  As with CSS properties, it is possible to access the spec for each property from the context menu.

<img src="img/properties-panel.png" alt="The properties sub-panel" />

DOM node objects inherit properties and functions from their parent objects. For example, a <code>p</code> element is represented in the DOM by a <code>HTMLParagraphElement</code> object, which inherits from <code>HTMLElementPrototype</code>, which in turn inherits from <code>ElementPrototype</code>, <code>NodePrototype</code> and finally the <code>Object</code> object. Each prototype that the currently selected DOM node object inherits from are listed along with their properties and functions. They can be expanded and inspected just like regular objects.

####Showing and hiding properties

It is possible to hide non-enumerable properties, and default values which are null or empty strings using the corresponding buttons on the properties toolbar.