There is a layout/rendering bug that only occurs in **read mode**. The same document renders correctly in live/edit mode.

### Current behavior

In read mode, some paragraphs are incorrectly laid out horizontally into multiple narrow fragments/columns instead of flowing as one continuous block of text.

For example, a paragraph that should render normally as:

> Renaming `F2`. Currently there is no quick access to rename the title of the document we're writing in. It should be renamed inline in our detail pane title header...

is visually split into several side-by-side text regions. Some words wrap into extremely narrow columns, causing sentences to appear vertically stacked or pushed sideways.

The underlying document content appears correct because the problem does not occur in live/edit mode.

### Expected behavior

Read mode should preserve normal document flow:

* Each paragraph should occupy the available content width.
* Text should wrap naturally within a single block.
* Inline elements such as keyboard shortcuts, bold text, links, or other formatting should remain inline without changing the paragraph's overall layout.
* A long paragraph should never create independent horizontal columns unless the document explicitly contains a multi-column layout.
* Read mode should visually match the text flow of live/edit mode as closely as possible.

### Suspected area

Please compare the DOM structure and CSS used by read mode against live/edit mode.

In particular, inspect whether the read-mode renderer is accidentally applying layout properties such as:

* `display: flex`
* `display: grid`
* `inline-flex`
* grid column definitions
* `width: min-content`
* `width: fit-content`
* inappropriate `flex: 1`
* `flex-wrap`
* `float`
* absolute positioning
* inherited width/max-width constraints

to paragraph nodes or their inline children.

Also check rendered rich-text nodes such as:

* paragraphs
* text spans
* keyboard shortcut / `<kbd>` elements
* strong/bold nodes
* links
* inline code
* custom rich-text components

An inline node should not cause neighboring text spans to become separate flex/grid children with independently calculated widths.

Do not solve this with fixed widths or manual per-element offsets. The goal is to restore normal block/inline text-flow semantics in the read-mode renderer.
