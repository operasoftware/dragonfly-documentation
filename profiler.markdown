##Profiler

Opera Dragonfly's Profiler gives developers a detailed behind-the-scenes look at the various operations performed by the browser, helping to identify potential problems and performance bottlenecks.

In broad terms, the operations performed by the browser will fall under the following categories:

* **Document parsing**: process the document's markup in order to construct its internal DOM representation
* **CSS parsing**: process any stylesheets, style blocks and attributes, user styles and the browser's own default stylesheet
* **Script compilation**: process any JavaScript, including JIT compilation
* **Thread evaluation**: actually run JavaScript code
* **Reflow**: starts the recalculation of the browser's render tree
* **Style recalculation**: based on the parsed CSS selectors, go through each relevant DOM node to determine if those particular style rules should be applied to it
* **Layout**: build the render tree
* **Paint**: display the calculated layout

The Profiler allows you to record and visualise this internal activity of the browser.

During normal debugging, Opera Dragonfly runs a series of background services, such as the ECMAScript debugger which disables JIT. Although these services facilitate script debugging, they would adversely affect profiling results. For this reason, before being able to use the Profiler, Opera Dragonfly will ask for the page to be reloaded and disable its background services. To use any of the other tabs or the HUD console, you will need to re-enable these default debugger features.

<img src="img/profiler-reload.png" alt="The Profiler tab, showing a reload button and the notice 'To get accurate data from the profiler, all other features have to be disabled and the document has to be reloaded.'">

To start profiling, click the record button. Any information about browser operations will now be collected. Clicking the record button again stops the recording session and displays the results.

One of the common use cases for profiling is to check the efficiency of how a page is first loaded and processed. Click the record button, enter a URL or simply reload the current page – either by clicking the reload button in the browser's interface, or using the <kbd>F5</kbd> / <kbd>CMD</kbd>+<kbd>R</kbd> key – and click the record button again after the page has finished loading.

Profiling can also be useful on an already-loaded page – for instance, to inspect what happens with timed JavaScript events, or to check how the browser reacts to user interactions defined on a page, such as dropdown menus, lightboxes, or complex XHR calls. The process to profile these is again the same: click record, wait/interact with the page, then click record again to finish the session and analyse the recorded data.

<img src="img/profiler-timeline.png" alt="The Profiler, showing the timeline of browser operations after a succesfull recording session">

The data recorded during the profiling session is presented in a timeline, divided into the various types of operations (**Document Parsing**, **CSS Parsing**, …) performed by the browser. Above the main timeline you will find a "mini timeline" that represents the entire length of the profiling session. From here you can zoom in on a specific timeframe by simply clicking and dragging a selection with the mouse. When an area has been selected, it can be moved by grabbing the selected area, or resized by dragging one of the edges. You can also resize or move the selection by using the mouse wheel or the arrow keys.

By default, all operations are displayed in the timeline. However, it's possible to filter out events with a short duration, displaying only events with a self-time greater than 1 ms, or only those exceeding 15 ms.

<img src="img/profiler-tooltip.png" alt="A Thread evaluation operation in the timeline being hovered, with a related tooltip displaying information relevant to that operation">

Hovering over an operation in the timeline displays a tooltip, listing the start time of the event (in the context of the recorded profiling session), the self-time of the operation itself, the overall duration of the operation (including any calls to child processes and follow-up operations), and additional context-dependent information: for **Document parsing**, **CSS parsing** and **Script compilation**, the related URL; for **Thread evaluation**, the type of thread involved; for **Paint** operations, the coordinates of the document that have been repainted. In addition, hovering over a **Paint** operation also highlights the repainted area in the document view itself.

The distinction between the duration and self-time can be best described through an example: usually, a **Reflow** (which may have been caused by a script inserting a new DOM node, for instance) results in a subsequent **Style recalculation**, **Layout** and **Paint** operation. Let's say that a reflow itself (with the browser invalidating the current render tree) takes 1ms - this would be its "self-time". However, the child calls for style recalculation, layout and paint will then take an additional 5ms to complete. So the overall duration of the entire reflow would be 6ms altogether. Visually, this distinction is represented by the different shades of colour used in each bar: the dark colour represents self-time, while the ligher shade indicates the overall duration.

### Details

Clicking on an operation in the timeline provides further details in an overlay panel. Note that this is currently only implemented for **Style recalculation** operations.

#### Style recalculations

This panel shows a table of all parsed CSS selectors that the browser matched against the DOM, the time it took to process them, and the number of match comparisons it performed.

<img src="img/profiler-style-recalculation-tooltip-details.png" alt="A highlighted style recalculation operation in the timeline, with the list of related CSS selectors in the details panel">

Note that the number of comparisons, listed as "hits", does not indicate the number of elements that a particular CSS selector was applied to, but rather reflects the number of elements the browser checked to determine if a selector would apply to them. This is directly related to the order in which browsers attempt to match CSS selectors from right to left.

As a trivial example, take the following HTML fragment

	<div id="foo">
	<p>first paragraph</p>
	<p>second paragraph</p>
	<p>third paragraph</p>
	</div>
	
	<div id="bar">
	<p>first paragraph</p>
	<p>second paragraph</p>
	<p>third paragraph</p>
	</div>

and an associated stylesheet containing the following rules

	#foo { ... }
	#foo p { ... }

Let's profile what happens when we load a page containing the above HTML fragment and style rules.

<img src="img/profiler-style-recalculation-details-example-hits.png" alt="Details view of the trivial example, showing the hits for '#foo' and '#foo p'">

If we look at the information panel, we see that `#foo` generated only a single hit, but `#foo p` caused 6 hits. This is because browsers will process style selectors from right to left, so in our example the browser will first gather all the `p` elements (inside both `#foo` and `#bar`), and then check if they have an ancestor matching `#foo`. In most situations, this shouldn't be a problem, but on very large documents, this sort of generic style selector can potentially add up to a big overhead. Note, however, that most browsers are able to optimise generic cases, like the one outlined above.