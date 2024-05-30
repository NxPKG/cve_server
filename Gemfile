source 'https://rubygems.org'

gem 'sinatra', '~> 2.0.8'
gem 'sinatra-contrib', '~> 2.0.8'
gem 'nokogiri', '~> 1.15.6'
gem 'mongo', '~> 2.10.1'
gem 'puma', '~> 5.6.8'

group :production do
  gem 'capistrano', '~> 3.11.0'
  gem 'capistrano-bundler', '~> 1.6.0'
  gem 'capistrano-rvm', '~> 0.1.2'
  gem 'capistrano3-puma', '~> 5.0.0'
end

group :development, :test do
  gem 'pry', '~> 0.12.2'
  gem 'rspec', '~> 3.8.0'
  gem 'rack-test', '~> 2.0.0'
  gem 'simplecov', '~> 0.17.0', :require => false
end

gem "tzinfo", "~> 2.0"
