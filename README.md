# quartermaster-site

The website for [Quartermaster](https://quartermaster.app): home page, User Guide and news. It's built with Jekyll and served by GitHub Pages. Templates live separately at [templates.quartermaster.app](https://templates.quartermaster.app) (`seanrogs/quartermaster-templates`).

## Editing

| What | Where |
| --- | --- |
| User Guide | `user-guide.md` (sidebar contents in `_data/guide.yml`; each `id` must match a `{#id}` heading) |
| News / release notes | `_posts/YYYY-MM-DD-slug.md` |
| Pages | `about.md`, `contact.md`, `donate.md`, `legal.md` |
| Links used site-wide (App Store, emails, PayPal) | `_config.yml` |
| Look and feel | `assets/css/site.css`, `_layouts/` |

To post release notes, copy the newest file in `_posts/` and change the date, title and body. Posts migrated from Tumblr keep their old `/post/<id>/<slug>` permalinks so existing links still work. New posts can leave `permalink` out.

## Preview locally

```bash
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --livereload
```

Then open http://localhost:4000.

## Short links

- `/get` redirects to the App Store
- `/privacy` redirects to seanr.org/privacy
- `/support` redirects to `/donate`, and `/archive` redirects to `/news` (Tumblr URLs)
- `www.quartermaster.app/user-guide` is linked from the app (`Links.swift`), so keep `/user-guide`.
