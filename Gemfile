source "https://rubygems.org"

# For local previews only — GitHub Pages builds with its own environment and ignores this file.
# These match the versions GitHub Pages uses (Jekyll 3.10 + the whitelisted plugins below).
# The github-pages meta-gem itself can't be used locally because it doesn't support Ruby 4 yet.
gem "jekyll", "~> 3.10"
gem "kramdown-parser-gfm"
gem "webrick"

group :jekyll_plugins do
  gem "jekyll-redirect-from"
  gem "jekyll-feed"
  gem "jekyll-sitemap"
  gem "jekyll-seo-tag"
end

# No longer bundled with Ruby 3.4+, but Jekyll 3 still needs them.
gem "csv"
gem "logger"
gem "base64"
gem "bigdecimal"
gem "ostruct"
