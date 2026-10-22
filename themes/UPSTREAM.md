# Vendored themes and search library

- PaperMod: [`adityatelange/hugo-PaperMod` commit `969bebdc5600a1639158b5ef4eff9cf6cbb511ac`](https://github.com/adityatelange/hugo-PaperMod/commit/969bebdc5600a1639158b5ef4eff9cf6cbb511ac), MIT license. The runtime source is in `PaperMod/`. Journal keeps its category, updated-date, home-intro, and style changes in that tree.
- hugo-video: [`martignoni/hugo-video` commit `fb3686a0156541bd21196fdfb185fe2ebc5f189f`](https://github.com/martignoni/hugo-video/commit/fb3686a0156541bd21196fdfb185fe2ebc5f189f), GPLv3 license. Its page-bundle video shortcode is retained because PaperMod's shortcode has different behavior.
- Fuse.js: [`krisk/Fuse` tag `v7.5.0`, commit `45bac9fe2e71fe8c680c861a35a8b226c4ae6d5a`](https://github.com/krisk/Fuse/releases/tag/v7.5.0), Apache-2.0 license. `PaperMod/assets/js/fuse.basic.min.mjs` is the upstream `dist/fuse.basic.min.mjs` Git blob `181c26b35a90598d22a0712000ffe5351fb425a1`; `PaperMod/assets/js/FUSE-LICENSE` carries the upstream license. The search script bundles it through Hugo's `js.Build`.

When refreshing these sources, select immutable upstream commits, compare runtime files and licenses, reapply the Journal changes, and check the rendered home page, post categories and dates, search, and video output before publishing.
