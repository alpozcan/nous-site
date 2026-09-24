# nous-site

The public website for **Nous AI Newsletter**, an iOS app that publishes one
daily edition of ranked artificial-intelligence news. "Nous" on its own is the
short name used in running prose; the App Store product name is the full one.

Live at <https://alpozcan.github.io/nous-site/>.

## What is here

| Path       | URL                                                   |
|------------|-------------------------------------------------------|
| `index.html`        | <https://alpozcan.github.io/nous-site/>          |
| `privacy/index.html`| <https://alpozcan.github.io/nous-site/privacy>   |
| `terms/index.html`  | <https://alpozcan.github.io/nous-site/terms>     |
| `support/index.html`| <https://alpozcan.github.io/nous-site/support>   |
| `licenses/supertonic-openrail-m.txt` | the voice model's licence, linked from the terms (OpenRAIL-M 4b) |

The privacy, terms and support URLs are the ones registered in App Store
Connect, so **their paths must not change**. Each is a directory with an
`index.html`, which is what gives the URLs no `.html` suffix.

## How it is built

It is not built. Four hand-written HTML files and one hand-written stylesheet,
served straight from the default branch by GitHub Pages. There is no framework,
no bundler, no package manager and no CI step: editing a file and pushing is the
whole deployment.

There is also nothing third-party on any page — no analytics, no scripts, no
webfonts, no external images, no cookies. The only subresource any page loads is
`style.css` from this repository. That is deliberate: a site whose main job is to
host a privacy policy should not itself contact anyone. The only external URLs
are ordinary links the reader can choose to follow (Apple's subscription
management, Apple's standard EULA, Apple's refund page).

Light and dark are both supported via `prefers-color-scheme`, the layout is
responsive down to phone width, and every page has a skip link, a real heading
outline and visible keyboard focus.

## Where the wording comes from

The prose in `privacy/`, `terms/` and `support/` began as the approved wording
the `nous-api` backend served at `/legal/privacy`, `/legal/terms` and `/support`,
generated from `src/lib/legal/` in that repository.

**The backend no longer serves those pages.** These files are the only published
privacy policy, subscription terms and support page there are, and the
`src/lib/legal/` generator is no longer the source of truth for them — this
repository is. Do not regenerate these pages from it; edit them here.

Hosting them here rather than on the backend means they keep answering even when
the API is down, being redeployed, or rewritten — which matters, because App
Store Connect requires the privacy and support URLs to resolve, and has no notion
of a page being temporarily unavailable.

Because there is no second copy to check against, treat an edit to these three
pages as a change to a published legal document: make it deliberately, and update
the `Last updated` date at the top of every page whose text changed.

### Renaming the product

The page paths carry no product name, so a rename never requires an App Store
Connect edit — only the copy changes. When renaming, use the full App Store name
where a page identifies the product (page title, `h1`, the "who is responsible"
clause in the privacy policy, the licence clause in the terms) and the short name
in running prose. The subscription tier is `Nous+` and does not track the app
name. `Settings → Notifications → Nous` on the support page is the app's
on-device display name (`CFBundleDisplayName`), not the App Store name, so it
changes only if that bundle key does.

## Contact

<hi@alp.me>
