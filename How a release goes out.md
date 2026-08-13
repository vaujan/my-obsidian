# How a release goes out
Writing this down because I re-derive it from the CI config every single time.

```mermaid
flowchart TD
    A[Merge to main] --> B[CI: lint + tests]
    B --> C{Green?}
    C -->|No| D[Fix forward]
    C -->|Yes| E[Tag vX.Y.Z]
    E --> F[Build + notarize]
    F --> G{Smoke test}
    G -->|Fails| D
    G -->|Passes| H[Publish + deploy docs]
```


## Gotchas

- Push the tag **after** CI is green on `main`. The build job reads the changelog from the commit
  the tag points at, so tagging early ships an empty release note.
- The Linux AppImage is built last and breaks the most often. Check it before announcing, not
  after.
- The docs deploy is independent of the app release, but release notes link into it — so if the
  notes reference a new page, deploy docs first.
