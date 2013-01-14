## Resources Inspector

The Resources Inspector gives an overview of all URI requests (such as images, scripts, stylesheets and XHR requests) initiated by a document.


<img src="img/resources-overview.png" alt="Opera Dragonfly's resources panel" />

The panel is split into two areas: a structured tree view of the document and all its resources, grouped by type, and a detailed resource view.

###Navigation, search and filter

Each expandable element of the tree features a bubble with the number of resources it holds. The elements can be expanded or collapsed with a single click. Clicking on an element while holding the <kbd>Shift</kbd> key will expand or collapse the element and all of its resources and child elements.

You can navigate through all expanded resources in the tree with the <kbd>↑</kbd> and <kbd>↓</kbd> cursor keys.

<img src="img/resources-filter-search.png" alt="Filtering and searching in Opera Dragonfly's resources panel" />

The URL filter lets you "prune" the tree view to only show resources matching a particular substring. This makes it easy to only list particular types of files (for instance, <code>.jpg</code> or <code>.js</code>) or only resources being served from a particular domain.

###Resource details

Selecting a resource in the tree view provides further information about that particular resource in the detailed view on the right. Depending on the type of resource, this will include the encoding, MIME type, guessed type, size, and resolution, as well as a link to open the resource in a new tab.

The major types of resources are recognized and displayed directly in the detailed resource view. In the case of web fonts, the detailed resource view not only gives a standard preview of the font, but also allows you to edit the sample string used for the preview.

<img src="img/resources-font.png" alt="Preview of an opentype font resource in the detailed resources view" />

For text-based resources (such as HTML or JavaScript), the search field can be used to find instances of a particular string. As usual, <kbd>F3</kbd> and <kbd>Shift</kbd>+<kbd>F3</kbd> moves between all highlighted results inside the resource.