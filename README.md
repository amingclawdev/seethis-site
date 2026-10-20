# seethis-site

Static website for [SeeThis](https://github.com/amingclawdev/seethis), served at https://seethis.dev by Cloudflare Pages.

- No build step. Cloudflare Pages settings: framework preset **None**, build command empty, output directory `/`.
- `main` deploys to production. Any other branch gets a preview URL for review before merging.
- `/download/` lets visitors choose the App Store or GitHub distribution; it never starts a download automatically. Keep each channel’s version, availability and update instructions separate.
- Demo videos and thumbnails are byte-identical copies of `docs/demo/` in the app repository; see that repo's `THIRD_PARTY_NOTICES.md` for media attribution.

## Channel short links

`_redirects` maps `/x`, `/th`, `/bs`, `/rd`, `/li` and `/yt` (X, Threads, Bluesky, Reddit, LinkedIn, YouTube) to the home page with a 302. Use the matching link when posting on each channel; Cloudflare's top-paths analytics then shows visits per channel.

## App Store release state

App Store version **0.1.1 (build 1)** is publicly available as **SeeThis: Visual Context**. Its listing was confirmed available on October 20, 2026: https://apps.apple.com/us/app/seethis-visual-context/id6818581322. The site links directly to that listing. GitHub **v0.1.1-beta.1** remains a separate direct-download option.

Public listing availability does not establish completed installation or first-launch validation.

For future release updates:

1. Keep the home-page release notice, FAQ and structured version data in `index.html` consistent with the public listing.
2. Update the Store card and metadata in `download/index.html`, and the availability sentence and CTA in `use-cases/numbered-marks/index.html`.
3. Preserve separate Store and GitHub versions, data-migration limits and permission steps. Do not reinstate automatic redirects.
4. Check the production listing and both download paths, then deploy through the reviewed `main` change.
