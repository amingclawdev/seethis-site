# seethis-site

Static website for [SeeThis](https://github.com/amingclawdev/seethis), served at https://seethis.dev by Cloudflare Pages.

- No build step. Cloudflare Pages settings: framework preset **None**, build command empty, output directory `/`.
- `main` deploys to production. Any other branch gets a preview URL for review before merging.
- `/download/` records the visit, then redirects to the current GitHub release DMG. Update its links when a new release ships.
- Demo videos and thumbnails are byte-identical copies of `docs/demo/` in the app repository; see that repo's `THIRD_PARTY_NOTICES.md` for media attribution.

## Channel short links

`_redirects` maps `/x`, `/th`, `/bs`, `/rd`, `/li` and `/yt` (X, Threads, Bluesky, Reddit, LinkedIn, YouTube) to the home page with a 302. Use the matching link when posting on each channel; Cloudflare's top-paths analytics then shows visits per channel.
