# modernized-js

> Maintained forks of unmaintained npm packages — modernized with full backwards compatibility.

## What we do

We pick up npm packages that have been deprecated or abandoned, **modernize the toolchain** (TypeScript, dual ESM + CJS, modern Node, strict lint, native test runner), and **keep the public API byte-compatible** so consumers can swap them in without code changes. Forks are re-published under the [`@modernized`](https://www.npmjs.com/org/modernized) npm scope.

## Packages

| Package | Original | Status |
| --- | --- | --- |
| [`@modernized/jpeg-exif`](https://www.npmjs.com/package/@modernized/jpeg-exif) | [`jpeg-exif`](https://www.npmjs.com/package/jpeg-exif) (deprecated) | ✅ Published |
| [`@modernized/arxiv-api`](https://www.npmjs.com/package/@modernized/arxiv-api) | `arxiv-api` | ✅ Published |
| [`node-fluent-ffmpeg`](https://github.com/modernized-js/node-fluent-ffmpeg) | `fluent-ffmpeg` | 🛠 In progress |
| [`exifr`](https://github.com/modernized-js/exifr) | `exifr` | 🛠 In progress |

## Migration

In most cases, swap the import:

```diff
- import x from 'package';
+ import x from '@modernized/package';
```

That's it — no other code changes needed.

## What "modernized" means

Each fork goes through the same arc:

1. **Toolchain swap** — replace legacy build/test deps with modern ones (`node:test`, ESLint 10 strict, Prettier, native coverage).
2. **TypeScript migration** — typed source with bundled `.d.ts`. No `any`, no `as` casts.
3. **Dual ESM + CJS publish** — `package.json` `exports` so both `import` and `require` work.
4. **Modern Node engine** — `engines.node: ">=22"`.
5. **Refactor for readability** — split monolithic files, drop module-level mutable state, tighten lint thresholds (complexity ≤ 15, max-lines-per-function ≤ 50).
6. **CI** — Linux / macOS / Windows × Node 22 / 24, with lint + typecheck + build + test + coverage gate.
7. **Release** — semantic version, tag, GitHub Release, npm publish.

The public API is **never** changed in a breaking way. Additive helpers (e.g. a Promise variant alongside a callback API) are fine.

## Contributing

If a package you depend on is unmaintained and you'd like a modernized fork:

- Open an issue on [the relevant repo](https://github.com/modernized-js)
- Or PR a new fork following the established pattern (TS, dual ESM/CJS, Node 22+, strict lint, native testing)
