source 'https://rubygems.org'

branch = ENV.fetch('SOLIDUS_BRANCH', 'master')
gem 'solidus', git: 'https://github.com/solidusio/solidus.git', branch: branch
gem 'solidus_auth_devise', '~> 1.0'

if branch == 'master' || branch >= "v2.3"
  gem 'rails', '~> 5.1.0' # HACK: broken bundler dependency resolution
elsif branch >= "v2.0"
  gem 'rails', '~> 5.0.0' # HACK: broken bundler dependency resolution
end

if ENV['DB'] == 'mysql'
  gem 'mysql2'
else
  gem 'pg', '~> 0.21'
end

group :test do
  if branch < "v2.5"
    gem 'factory_bot', '4.10.0'
  else
    gem 'factory_bot', '> 4.10.0'
  end
end

gemspec
