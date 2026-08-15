# Goal: semantic search over \~3k notes, fully offline, no server. The index has to sit next to the

existing PouchDB database and survive sync.

This is meant to sit _alongside_ keyword search, not replace it — see

## Candidates

* 👍 [sqlite-vec](https://github.com/asg017/sqlite-vec)
  * Single C file, no extra process, runs anywhere SQLite already runs
  * Brute-force KNN only — fine at 3k vectors, questionable at 100k
* 😕 [hnswlib-node](https://github.com/yoshoku/hnswlib-node)
  * Fast approximate search, but it's a native addon → ABI-locked to the Electron version
  * Rebuilding it on every Electron bump is exactly the maintenance I'm trying to avoid
* 🤔 [LanceDB](https://github.com/lancedb/lancedb)
  * Embedded, columnar, handles updates well
  * Ships its own storage format — a second database to back up, migrate, and explain

## Rough sizing

3,000 notes × 384 dimensions × 4 bytes ≈ 4.6 MB of vectors. Small enough that a brute-force scan
is bound by memory bandwidth rather than algorithm choice, so an approximate index buys nothing
until the corpus is \~50× bigger.

## Leaning toward sqlite-vec

* [x] Confirm it loads inside a packaged Electron build
* [x] Measure query latency at 3k and 30k vectors
* [x] Decide where embeddings get computed — on-device model, or a batch job on save
* [x] Work out what sync does: are embeddings replicated, or recomputed per device?
