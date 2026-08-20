# BM25 for ranking search results

Reading up on ranking before I touch the search index. Results are currently sorted by
`updatedAt`, which is fine for a handful of hits and useless past a few hundred.

- [Okapi BM25 - Wikipedia](https://en.wikipedia.org/wiki/Okapi_BM25)

## The score

For a query $q$ with terms $q_1 \dots q_n$ against a note $D$:

```math
\text{score}(D, q) = \sum_{i=1}^{n} \text{IDF}(q_i) \cdot \frac{f(q_i, D) \cdot (k_1 + 1)}{f(q_i, D) + k_1 \cdot \left(1 - b + b \cdot \frac{|D|}{\text{avgdl}}\right)}
```

where $f(q_i, D)$ is the term frequency, $|D|$ the note length in words, and $\text{avgdl}$ the
average note length across the notebook.

The interesting knob is $b$ — how hard a long note gets penalized. At $b = 0$ length is ignored
entirely, at $b = 1$ it's fully normalized. Common defaults: $k_1 \in [1.2, 2.0]$, $b = 0.75$.

## Why it matters here

My own notes are wildly uneven — a 40-word "tmux italics not working" sitting next to a
4,000-word project log. Plain term frequency ranks the long one higher just because it repeats
the word more often, which is exactly what the $\frac{|D|}{\text{avgdl}}$ term corrects for.

## Next

- Check what PouchDB's search plugin already does — this might be free
- $\text{avgdl}$ has to be maintained incrementally; recomputing it per query means a full scan

Keyword ranking only. The semantic side is a separate question, tracked in
[Pick a local vector store for semantic search](inkdrop://note/Ew1tGx9Z).
