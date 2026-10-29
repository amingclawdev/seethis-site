# seethis-site

Static website for [SeeThis](https://github.com/amingclawdev/seethis), served at https://seethis.dev by Cloudflare Pages.

- No build step. Cloudflare Pages settings: framework preset **None**, build command empty, output directory `/`.
- `main` deploys to production. Any other branch gets a preview URL for review before merging.
- `/download/` lets visitors choose the App Store or GitHub distribution; it never starts a download automatically. Keep each channel’s version, availability and update instructions separate.
- Demo videos and thumbnails are byte-identical copies of `docs/demo/` in the app repository; see that repo's `THIRD_PARTY_NOTICES.md` for media attribution.

## Channel short links

`_redirects` maps `/x`, `/th`, `/bs`, `/rd`, `/li` and `/yt` (X, Threads, Bluesky, Reddit, LinkedIn, YouTube) to the home page with a 302. Use the matching link when posting on each channel; Cloudflare's top-paths analytics then shows visits per channel.

## Release state

The site describes **0.1.5** (updated October 29, 2026) on both channels. GitHub release **v0.1.5** (https://github.com/amingclawdev/seethis/releases/tag/v0.1.5) is published; the download page links its DMG, ZIP and SHA256SUMS. On the Mac App Store, 0.1.5 was released on October 29, 2026; the listing, **SeeThis: Show AI What You Mean** (https://apps.apple.com/us/app/seethis-visual-context/id6818581322), has **0.1.5**. The home page buttons go to the Store listing; the download page offers both.

The four scenario videos in `assets/scenarios/` are the v3 16:9 story masters from the SeeThis promo project with its music and sound-effects mix (Mixkit, free license; reference access keys hidden), saved with `+faststart`; the posters are frames from the same files. When a video changes, bump the `?v=` query on its links in `index.html`: `/assets/*` is cached for 7 days.

For future release updates:

1. Keep the home-page release notice, FAQ and structured version data in `index.html` consistent with the public listing.
2. Update the Store card and metadata in `download/index.html`, and the availability sentence and CTA in `use-cases/numbered-marks/index.html`.
3. Preserve separate Store and GitHub versions, data-migration limits and permission steps. Do not reinstate automatic redirects.
4. Check the production listing and both download paths, then deploy through the reviewed `main` change.
