# seethis-site

Static website for [SeeThis](https://github.com/amingclawdev/seethis), served at https://seethis.dev by Cloudflare Pages.

- No build step. Cloudflare Pages settings: framework preset **None**, build command empty, output directory `/`.
- `main` deploys to production. Any other branch gets a preview URL for review before merging.
- `/download/` lets visitors choose the App Store or GitHub distribution; it never starts a download automatically. Keep each channel’s version, availability and update instructions separate.
- Demo videos and thumbnails are byte-identical copies of `docs/demo/` in the app repository; see that repo's `THIRD_PARTY_NOTICES.md` for media attribution.

## Channel short links

`_redirects` maps `/x`, `/th`, `/bs`, `/rd`, `/li` and `/yt` (X, Threads, Bluesky, Reddit, LinkedIn, YouTube) to the home page with a 302. Use the matching link when posting on each channel; Cloudflare's top-paths analytics then shows visits per channel.

## App Store release state

The site currently says **approved — release in progress** for App Store 0.1.1 (build 1). The listing URL is https://apps.apple.com/us/app/seethis-visual-context/id6818581322; it is kept in a comment beside the Store card until public availability is confirmed, rather than sending visitors to an unavailable listing. GitHub v0.1.1-beta.1 remains available.

After the public listing is confirmed available for download:

1. Update the release notice and distribution FAQ in `index.html`, and the availability sentence in `use-cases/numbered-marks/index.html`.
2. In `download/index.html`, change the Store card from pending to available and add a clear App Store download action using the saved listing URL; update the meta description and remove conditional availability wording from the update guidance.
3. Preserve separate Store and GitHub versions, data-migration limits and permission steps. Do not reinstate automatic redirects.
4. Check the production listing and both download paths, then deploy through the reviewed `main` change. The local release-state edit alone does not establish Store availability.
