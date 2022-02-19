source "https://rubygems.org"
ruby RUBY_VERSION

gem "jekyll-remote-theme"

gem "github-pages",  ">= 223", group: :jekyll_plugins
# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.15"
  gem "jekyll-paginate", "~> 1.1"
  gem "jekyll-seo-tag", "~> 2.7"
  gem "kramdown-parser-gfm", "~> 1.1"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo-data"
end

gem "webrick", "~> 1.7"
