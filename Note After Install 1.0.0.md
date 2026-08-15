# Notable Issues

* **Confirm/Check:** We should confirm the existing implementation about the image embedding feature. We should check how image is embedded and how it looks like in the Markdown source
* **Confirm/Check:** Scrolling through the main item visual rails is 'kind of' heavy. Is it normal because each note item is rendering 'markdown'? It happens in 100 notes, not after 1000
* Writing down markdown doesn't feel any different from this app to other app? 
* Right-clicking in our index item doesn't open the context menu
* Cannot access developer tools  via `f12`
* Zen mode key toggle doesn't works
* ![](./image-2026-08-15-144635.png)The selected UI indicator should look like this, it should use the 'active' item state without the left border for indicator
* Date system should also follow created and updated, not only updated. The index item rail keep showing 'Just now' everytime we update or if any changes occur. This doesn't provide a useful information for the user when is the item created (which more important than 'Just now' everytime')
* Badge redesign for a11y, add a bit border
* When our notes it scrolled away, toggling from live mode to read mode behaves normally. But from read mode to live mode, we immediately scrolled to the beginning line and is prompted to write from the starting point of the document

# Features For Later Improvement

* ![](./image-2026-08-15-145253.png)The active cursor is at the bottom of the page when we extend a new document further than the height of the pane. It is very 'packed' and need more space/room 
* What is the recommended settings for performance also for aesthetic? The user should also can picked which one suits their needs the best
* Pin notes? The goal of this feature is to provide user a way to put item on a 'watchlist', that they constantly looking up to or providing updates to
