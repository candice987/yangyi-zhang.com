source "https://rubygems.org"

# Ruby 4.0 移除了 csv / base64 等标准库，需显式声明
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"
gem "ostruct"

# Jekyll 4.x —— 与 Ruby 4.0 兼容
# 注意：GitHub Pages 部署时使用自带的 Jekyll 版本，本地版本无需完全一致
gem "jekyll", "~> 4.3"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
  gem "jekyll-seo-tag", "~> 2.8"
  gem "jekyll-sitemap", "~> 1.4"
end

# Windows / JRuby 兼容
gem "tzinfo-data", platforms: [:windows, :jruby]
gem "wdm", "~> 0.2.0", platforms: [:windows] if Gem.win_platform?
