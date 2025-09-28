# frozen_string_literal: true
source "https://rubygems.org"

ruby "3.2.4"  # più compatibile su Netlify (puoi usare 3.3.4, ma 3.2.4 è più “tranquilla”)

gem "jekyll-theme-chirpy", "~> 7.0", ">= 7.0.1"

# Evita la versione con estensioni C
gem "json_pure", "~> 2.6"

group :test do
  gem "html-proofer", "~> 5.0"
end

# Solo per sviluppo locale con `bundle exec jekyll serve`
gem "webrick", group: :development
