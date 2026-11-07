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

## Posting news

1. Add a file named `_posts/YYYY-MM-DD-short-name.md`, for example `_posts/2026-12-01-quartermaster-67.md`. The date in the name is the post's date.
2. Start it with this header, then write the post in Markdown:

   ```markdown
   ---
   title: "Quartermaster 6.7"
   tags: [quartermaster, app store, updates]
   ---
   The first paragraph is the summary shown on the home page and News page.

   ## A heading

   More text, **bold**, [links](https://example.com), lists and so on.
   ```

3. Commit and push to `main`. GitHub Pages rebuilds the site and the post is live within a minute or two (watch the **Actions** tab).

Header fields:

- `title` is the only required field. `tags` is optional.
- `date: 2026-12-01 09:00:00 +1000` sets the time of day. Without it, the date comes from the filename.
- `published: false` keeps a post hidden. Delete the line when it's ready to go live.
- Leave out `permalink`. Only posts migrated from Tumblr need it, to keep their old `/post/<id>/<slug>` addresses working.

Images and links:

- Put images in `assets/posts/<folder>/` and link them with `![Description]({{ '/assets/posts/<folder>/1.jpg' | relative_url }})`.
- Link to other pages the same way, for example `[Traits]({{ '/user-guide#traits' | relative_url }})`.
- `relative_url` keeps links working on both the github.io preview address and quartermaster.app.

Watch out for:

- **Future dates:** a post dated in the future won't appear when you push it. GitHub Pages doesn't rebuild on its own, so it stays hidden until the next push after that date. Date it today, or use `published: false` until it's ready.
- **Preview first** with the steps below. Open `/news` to check it, and add `--unpublished` to `jekyll serve` to see hidden drafts.

## Preview locally

```bash
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --livereload
```

Then open http://localhost:4000/quartermaster-site/ (or http://localhost:4000 once `baseurl` in `_config.yml` is back to `""` for quartermaster.app).

## Short links

- `/get` redirects to the App Store
- `/privacy` redirects to seanr.org/privacy
- `/support` redirects to `/donate`, `/archive` to `/news`, and `/userguide` to `/user-guide` (Tumblr URLs, still used by templates.quartermaster.app)
- `www.quartermaster.app/user-guide` is linked from the app (`Links.swift`), so keep `/user-guide`.
