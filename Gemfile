source "https://rubygems.org"
source "https://rails-assets.org"

#ruby "2.2.10" # come from originL Gemfile
ruby "2.3.8"

gem "rails", "4.2.6"

# protected_attributes is included as part of the Rails 4 upgrade. It would be
# great if we weren't using this, but moving all the controllers to
# strong_params is a fairly hefty effort, and this is probably acceptable
# technical debt for the moment.
gem "protected_attributes"

# Rails observers are deprecated in Rails 4, but the functionality has been
# extracted to a gem, so to avoid reworking all our observers as part of the
# Rails 4 upgrade, simply include that gem for now.
gem "rails-observers"

# Include rack-cache for staging/production environments.
# See http://stackoverflow.com/a/26552572/2240218
gem "rack-cache"

gem "jquery-rails",  "< 3.0.0"
gem "bugsnag", "~>3.0.0"
# locking gem "rake" to < 11.2.3"
gem "rake", "< 11.2.3"
gem "childprocess"
gem "squeel"
gem "friendly_id"
gem "cancan"
gem "puma"
gem "sidekiq"
# Needed to use sidekiq dash
gem "sinatra", :require => nil
gem "sidekiq-statistic"
gem "sidekiq-failures"

gem "sprockets-rails", ">= 2.3.2"
gem "bootstrap", "~> 4.0.0.alpha3"
gem "font-awesome-sass", "~> 4.5.0"

gem "haml-rails"
gem "simple_form"
gem "devise"
gem "devise_invitable"
gem "omniauth", "~>1.6.1"
gem "omniauth-facebook", "~>4.0.0"
gem "hpricot"
gem "ruby_parser"
gem "will_paginate", "~> 3.0"
gem "json"
gem "rest-client"
gem "awesome_print"
gem "lll"
gem "quiet_assets"
gem "factory_girl", "= 4.1.0"
gem "factory_girl_rails", "= 4.1.0"
# The factory_girl gem is deprecated. Upgrading to factory_bot.
# gem "factory_bot_rails", "~> 4.0"
gem "ffaker"
gem "redcarpet"
gem 'rabl'
gem 'memoist'
gem 'uuid'
gem "symbolize", :require => "symbolize/active_record"
gem 'eventmachine'
gem "dalli"
gem "memcachier"
gem "draper"
gem "paperclip"
gem 'aws-sdk', '~> 1.3.4'
gem "nokogiri"
gem "tire"
# http://reefpoints.dockyard.com/ruby/2012/06/18/postgres_ext-adding-postgres-data-types-to-active-record.html
gem 'postgres_ext'
gem "colored"
gem "curb"
gem "rmagick", "= 3.1.0"
gem "stripe", "= 1.8.4"
gem "stripe_event", "=  0.6.0"
gem "gon"
gem "paper_trail"
gem "diffy"
gem "js-routes"
gem "active_model_serializers", "= 0.8.3"

gem "email_reply_parser"
gem "mail", "~>2.6.6"


# Used for pre-loading info about users
gem "clearbit"
gem "nestful", "1.1.0"

# We use Redis even outside of our gem dependencies
gem "redis"

# Mail related gems --------
gem 'device_detector'
# Roadie versions of 3.x has a significantly different API. 2.4.3 is the
# highest version that is compatible with Rails 4, so lock to this
gem "roadie-rails"

# Rails Assets
gem "rails-assets-angular", "~>1.5.8"
gem "rails-assets-angular-resource"
gem "rails-assets-angular-cookies"
gem "rails-assets-angular-animate"
gem "rails-assets-tether", ">= 1.1.0"
gem "rails-assets-js-data"
gem "rails-assets-js-data-angular"
gem "rails-assets-angular-ui-router"
gem "rails-assets-moment"
gem "rails-assets-angular-moment"
gem "rails-assets-angular-elastic"
gem "rails-assets-angular-sanitize"
gem "rails-assets-underscore"
gem "rails-assets-alertifyjs"
gem "rails-assets-angular-bootstrap"
gem "rails-assets-angular-utils-pagination"
gem "rails-assets-ngtouch"
gem "rails-assets-angular-upload"

# Pusher
gem "pusher"

gem "angular-rails-templates", "~>1.0"
gem "sprockets", "~> 3.6.0"


# best to keep as low as possible, see
# https://newrelic.com/docs/ruby/ruby-agent-installation#Using_Bundler
gem "newrelic_rpm", "~> 3.0"

# We may be able to drop sass-rails and coffee-rails by moving to Rails 4, as I
# think they get included by Rails anywawy, but for the moment I've left them
# in.
gem "sass-rails"
gem "coffee-rails"
gem "uglifier"
gem "therubyracer"

gem "mixpanel-ruby"

# group :production, :staging, :stagingflorent do
group :production do
# locking pg to 0.20 - to solve issue: PGconn, PGresult, and PGError constants are deprecated"
  gem "pg", "< 0.21"
  #gem "rack-timeout"
  gem "rails_12factor"
end


group  :test do
  # Rails 4 compatibility came in at this version of rspec 2, and not ready to
  # go through the rigmarol of upgrading to rspec 3 yet:
  # https://relishapp.com/rspec/rspec-rails/docs/upgrade
  gem "rspec-rails", "> 3"
  gem "capybara", ">= 2.5.0"
  gem "capybara-webkit", "~>1.7.1"
  gem "capybara-screenshot"
  gem "email_spec"
  gem "rb-fsevent"
  gem "launchy"
  gem "timecop"
  gem "webmock", require: false
  gem "rspec_junit_formatter", "0.2.2"
  # Needed to make after_commit work in tests (needed for Sidekiq)
  gem "test_after_commit"
end

group :test, :development, :test_perf do
  # track master for this fix:
  # https://stackoverflow.com/questions/24030907/spork-0-9-2-and-rspec-3-0-0-uninitialized-constant-rspeccorecommandline-n
  gem 'spork', github: 'sporkrb/spork', branch: 'master'
  gem "guard-spork"
  gem "guard-rspec"
  gem "dotenv-rails"
  gem "pry-rails"
  gem "pry-remote"
  # works for Firefox 45
  gem "selenium-webdriver", "~>2.53.4"
  # locked to not interfere with pry-remote
  gem "pry-byebug", " = 1.3.3"
end

group :development do
  gem "proxylocal"
  gem "pony"
  gem "highline" # used by the deployer
  gem 'growl' # used by the deployer
  gem "thin" # to avoid debug message from Webrick http://stackoverflow.com/a/10249298/117704
  gem 'sys-proctable'
  gem 'ultrahook' # used to proxy requests to localhost
  gem 'activerecord_sane_schema_dumper'
  gem 'meta_request'
end
