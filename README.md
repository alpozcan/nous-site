# nous-site

The public website for **Nous**, an iOS app that publishes one daily edition of
ranked artificial-intelligence news.

Live at <https://alpozcan.github.io/nous-site/>.

## What is here

| Path       | URL                                                   |
|------------|-------------------------------------------------------|
| `index.html`        | <https://alpozcan.github.io/nous-site/>          |
| `privacy/index.html`| <https://alpozcan.github.io/nous-site/privacy>   |
| `terms/index.html`  | <https://alpozcan.github.io/nous-site/terms>     |
| `support/index.html`| <https://alpozcan.github.io/nous-site/support>   |

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

The prose in `privacy/`, `terms/` and `support/` is the approved wording that the
Nous backend used to serve at `/legal/privacy`, `/legal/terms` and `/support`,
copied verbatim. Its generator lives in the `nous-api` repository under
`src/lib/legal/`.

These pages are now the canonical, published versions. Hosting them here rather
than on the backend means they keep answering even when the API is down or being
redeployed — which matters, because App Store Connect requires the privacy and
support URLs to resolve.

If the wording changes, change it here, and update the `Last updated` date at the
top of the page that changed.

## Contact

<hi@alp.me>
