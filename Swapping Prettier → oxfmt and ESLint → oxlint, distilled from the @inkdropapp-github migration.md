Swapping Prettier → oxfmt and ESLint → oxlint, distilled from the `@inkdropapp/github` migration
so I can copy-paste it next time.

> **Verify versions first** — these tools move fast, so pin what you check instead of copying
> from memory.
>
> ```sh
> pnpm view oxlint version    # was 1.68.0
> pnpm view oxfmt version     # was 0.53.0 (still pre-1.0, intentionally)
> ```

## Swap the dependencies

```sh
pnpm remove eslint @eslint/js typescript-eslint eslint-config-prettier \
            prettier @ianvs/prettier-plugin-sort-imports
pnpm add -D oxlint oxfmt
```

## Config

```json
{
  "$schema": "./node_modules/oxfmt/configuration_schema.json",
  "semi": false,
  "singleQuote": true,
  "trailingComma": "none",
  "sortImports": true,
  "sortPackageJson": true
}
```

| option          | Prettier default | oxfmt default | set to   |
| --------------- | ---------------- | ------------- | -------- |
| `semi`          | `true`           | `true`        | `false`  |
| `singleQuote`   | `false`          | `false`       | `true`   |
| `trailingComma` | `"all"`          | `"all"`       | `"none"` |

`sortImports: true` replaces `@ianvs/prettier-plugin-sort-imports`. Don't set `printWidth`.
`oxfmt --migrate=prettier` converts an existing config; `oxlint --init` scaffolds
`.oxlintrc.json`.

For oxlint, `categories.correctness: "error"` is the conservative likely-bugs set and the right
default. Rule names map `@typescript-eslint/foo` → `typescript/foo`; core rules keep their bare
name. Nothing like `eslint-config-prettier` is needed — oxlint has no formatting rules to
conflict with.

## Gotchas

* **oxlint reads only the _local_ `.gitignore`.** If `node_modules` isn't in it, a bare `oxlint`
  lints the entire dependency tree and explodes. Add `"node_modules/**"` to `ignorePatterns`.
  oxfmt skips it natively.
* **`sortImports` is more opinionated than `@ianvs`.** It groups third-party and internal imports
  with a blank line between them, so expect a one-time diff.
* **oxfmt is pre-1.0** — output can shift between minors. Pin it and bump deliberately.
* A failing `tsc` afterwards is usually a separate tsconfig problem, not oxc's fault. Run the
  build before declaring victory.

## Verify

```sh
pnpm install
pnpm format    # apply once, then review the import-grouping diff
pnpm lint      # expect exit 0
pnpm typecheck && pnpm build
```
