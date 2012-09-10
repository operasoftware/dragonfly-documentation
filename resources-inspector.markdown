## Resources Inspector

The Resources Inspector gives information for each URI of a webpage. An overview of all URI requests (images, scripts, style, etc.) initiated by the primary webpage (primary HTTP request) is provided.

### Understanding the Resources Inspector panel

The Resources Inspector has 5 columns listing information about the primary requested resource and all dependent resources.

![Resources View](img/resources-view.jpg)

For each resource, The following information is given:

* A colored icon to quickly visualize the type of resources (images, scripts, markup, etc.)
* The host part of the URI
* The path part of the URI
* The type of content associated with this URI
* The size of the resource (in a human readable format)

Additional options are available by pressing <kbd>ctrl</kbd>+click. It is possible to add columns for protocols (such as HTTP or HTTPS), the MIME type of the content, and the size in bits. Columns can be removed by unchecking them.  

When clicking on a specific line, a new tab opens with the source code for an HTML resource, or the rendered image for an image resource. Further details such as size and format can be found by clicking on the plus arrow sign. 

![Expanding an individual resource shows further details about the resources](img/resources-detail-expand.jpg)

Once the source code is visible, a search box appears at the top right of the window. Typing a keyword will highlight this keyword in the source code. Press the return key successively to access other occurrences of the keyword in the source. Once the bottom has been reached, it cycles again from the top of the document.

![Searching for a string of text inside the resource file](img/resources-search.jpg)

The first tab is the <q>All resources</q> view. When pressing Ctrl+click in this window, a menu appears. Resources can then be organized by hosts or by type.

![Context menu showing the various grouping options available for the resource view](img/resources-grouping-options.jpg)

Selecting "Group by Host" will reorder the resource list alphabetically by host. This provides a quick way to identify a specific set of URIs for each domain. A hint about missing resources is provided should those resources be unavailable.

![Resources reordered and grouped by host](img/resources-by-host.jpg)

To focus on a specific resource by type, select the "Group by Type" option. All styles, all images and all HTML resources will then be grouped together.

![Resources reordered and grouped by type](img/resources-by-type.jpg)

### What are URIs?

URI, or Universal Resource Information, is a way to identify resources on the Web. When we GET a URI with a browser, we receive a representation of a given resource. The resource might have multiple representations such as language features. The most important aspect of a URI to remember is that URIs are not files, rather, they are the representation of the resource.


