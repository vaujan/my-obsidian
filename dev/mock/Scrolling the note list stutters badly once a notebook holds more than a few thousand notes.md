Scrolling the note list stutters badly once a notebook holds more than a few thousand notes.
Reproduced on my own database (3,040 notes) — the FPS meter drops to \~20 while dragging the scrollbar.

***

## Profile first

* [Analyze runtime performance | Chrome DevTools](https://developer.chrome.com/docs/devtools/performance/)

Recorded a 4-second scroll:

```
Scripting   2,140 ms
Rendering     680 ms
Painting      210 ms
Idle           95 ms
```

So it's scripting-bound, not paint-bound. 🤔

## ✅ Every row re-renders on scroll

`NoteListItem` isn't memoized, so a scroll-position change re-renders all 3,040 of them.

```tsx
export const NoteListItem = memo(function NoteListItem({ note, active }: Props) {
  // ...
})
```

* [`memo` – React](https://react.dev/reference/react/memo)

Scripting drops to 380 ms. Good enough to ship, but the whole list is still mounted.

## 🤔 Windowing the list

* [react-window](https://github.com/bvaughn/react-window)

Rendering $n$ rows costs roughly $c \cdot n$, and windowing replaces $n$ with the $v$ rows
actually on screen. At $n = 3040$ and $v = 24$:

$$
\frac{n}{v} \approx 127
$$

...two orders of magnitude fewer mounted rows. Blocked on the sticky pinned-notes header, which
assumes every row is in the DOM.

## Next

* [x] Memoize `NoteListItem`
* [x] Verify against a 10k-note database
* [ ] Windowed list behind a config flag ✅ 2026-08-13
* [ ] Re-test on the iPad app ✅ 2026-08-13
