# modernized-js

**Maintained forks of unmaintained npm packages, kept byte-compatible.**

[📦 npm scope: @modernized](https://www.npmjs.com/org/modernized) · [💬 Suggest a package](https://github.com/modernized-js/.github/issues/new)

> [!NOTE]
> **Drop-in replacement.** Change the import path. That's all.
>
> ```diff
> - import x from 'package';
> + import x from '@modernized/package';
> ```

## Packages

| Package | npm | Original | Status |
| --- | --- | --- | --- |
| [**`@modernized/jpeg-exif`**](https://github.com/modernized-js/jpeg-exif) | [![npm](https://img.shields.io/npm/v/@modernized/jpeg-exif.svg)](https://www.npmjs.com/package/@modernized/jpeg-exif) [![dl](https://img.shields.io/npm/dm/@modernized/jpeg-exif.svg)](https://www.npmjs.com/package/@modernized/jpeg-exif) | [`jpeg-exif`](https://www.npmjs.com/package/jpeg-exif) (deprecated) | ✅ Published |
| [**`@modernized/arxiv-api`**](https://github.com/modernized-js/arXiv-api) | [![npm](https://img.shields.io/npm/v/@modernized/arxiv-api.svg)](https://www.npmjs.com/package/@modernized/arxiv-api) [![dl](https://img.shields.io/npm/dm/@modernized/arxiv-api.svg)](https://www.npmjs.com/package/@modernized/arxiv-api) | [`arxiv-api`](https://www.npmjs.com/package/arxiv-api) | ✅ Published |
| [**`@modernized/fluent-ffmpeg`**](https://github.com/modernized-js/node-fluent-ffmpeg) | [![npm](https://img.shields.io/npm/v/@modernized/fluent-ffmpeg.svg)](https://www.npmjs.com/package/@modernized/fluent-ffmpeg) [![dl](https://img.shields.io/npm/dm/@modernized/fluent-ffmpeg.svg)](https://www.npmjs.com/package/@modernized/fluent-ffmpeg) | [`fluent-ffmpeg`](https://www.npmjs.com/package/fluent-ffmpeg) (deprecated) | ✅ Published |
| [**`@modernized/exifr`**](https://github.com/modernized-js/exifr) | [![npm](https://img.shields.io/npm/v/@modernized/exifr.svg)](https://www.npmjs.com/package/@modernized/exifr) [![dl](https://img.shields.io/npm/dm/@modernized/exifr.svg)](https://www.npmjs.com/package/@modernized/exifr) | [`exifr`](https://www.npmjs.com/package/exifr) | ✅ Published |

## What we do

- 🦺 **TypeScript source** with bundled `.d.ts` — strict typing, no `any`, no `as` casts
- 📦 **Dual ESM + CJS publish** — both `import` and `require` work out of the box
- 🟩 **Modern Node** — `engines.node: ">=22"`
- 🧪 **Native test runner** — `node:test` + `node:assert`, coverage gated in CI (90 / 70 / 90)
- 🧹 **Strict lint** — ESLint 10 + `unicorn` + `promise`, complexity ≤ 15, max-lines-per-function ≤ 50
- ✅ **CI matrix** — Linux / macOS / Windows × Node 22 / 24
- 🔒 **API stays byte-compatible** — no breaking changes; new functionality is additive only

## Suggest a package

Got a dependency that's been abandoned and you'd love a modernized fork?

> [!TIP]
> **Org-level requests** (please fork X, roadmap ideas) → [`modernized-js/.github` issues](https://github.com/modernized-js/.github/issues)
>
> **Package-specific bugs / improvements** → that package's own repo (e.g. [`modernized-js/jpeg-exif`](https://github.com/modernized-js/jpeg-exif/issues))
>
> **Or open a PR** with a new fork following the established pattern: TS, dual ESM/CJS, Node 22+, strict lint, native testing.

## How a fork is modernized

Each fork goes through the same arc:

1. Import the upstream tarball into a fresh repo, preserve the original LICENSE / authorship.
2. Replace the build / test / lint toolchain.
3. Migrate source to TypeScript (`git mv` so history follows).
4. Add a dual ESM + CJS build via `tsc` × 2 configs.
5. Refactor for readability — split monolithic files, drop module-level mutable state.
6. Tighten lint, gate CI on coverage.
7. Tag, GitHub Release, npm publish under `@modernized`.
