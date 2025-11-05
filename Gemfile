source 'https://rubygems.org'

gem 'jekyll', '~> 4.3.0'
gem 'minima'
gem 'sass-embedded', '~> 1.69.0'

group :jekyll_plugins do
  gem 'jekyll-algolia', '~> 1.0'
  gem 'jekyll-sitemap'
  gem 'jekyll-feed'
end

# Platform-specific gems
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem 'tzinfo', '>= 1', '< 3'
  gem 'tzinfo-data'
end

# Performance-booster for watching directories on Windows
gem 'wdm', '~> 0.1.1', :platforms => [:mingw, :x64_mingw, :mswin]
