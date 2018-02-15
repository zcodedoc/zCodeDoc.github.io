---
layout: post
title:      "Rails Tests Setup"
date:       2018-02-15 23:00:55 +0000
permalink:  rails_tests_setup
---


When it comes to testing I've found the first difficult task to even begin to start testing is
the setup. Here's a step-by-step guide of what I did to setup tests for my Rails API
models.

**NOTE**: This guide is being created from a Rails 5 project that has been created **without** the built in test suite and already had its associations set up.

1) In the Gemfile create `group :develop, :test` block
* this block will install gems that both the developement and test environments will use

2) add these gems to the block
* `rspec-rails` - provides the RSpec framework for our test
* ` factory_bot_rails` (using the rails version adds helpers for generators)
  - factory_bot has replaced the depreciated factory_girl gem
  - it is a smart replacement for fixtures (fixtures are reusable test data info)
  - allows you to create sample data for your tests
* `faker` - a library that generates fake data

3) In the Gemfile create `group :test` block
* this block is specifically for gems in the test environments

4)  add these gems to the block
* `shoulda-matchers` - easily allows RSpec to test associatons and validations of our models as well as other common Rails functionality  
* `database_cleaner` - cleans the test database

5) `bundle` to install new gems

6) run `rails generate rspec:install` - this will create the spec directory
* the folder consists of .rspec, spec/spec_helper.rb and spec/rails_helper.rb

7) open `spec/rails_helper.rb`, lets setup the database_cleaner gem
* add `require 'database_cleaner'` under `require 'spec_helper'` - giving the file access to the
gem 
* In the RSpec.configure block add: 
```
config.before(:suite) do
    DatabaseCleaner.clean_with(:truncation)
    DatabaseCleaner.strategy = :transaction
end
``` 
  - this means at first truncate all the tables in the database, but then use the faster transaction strategy the remaining time
 
* next, attach this code below the one above:
```
config.around(:each) do |example|
    DatabaseCleaner.cleaning do
    example.run
end
```
  - here we're telling the gem to clean the database as the examples are run

8)  now we'll configure the shoulda - matchers gem
* also inside `spec/rails_helper.rb` below this line `ActiveRecord::Migration.maintain_test_schema!` insert this block:
```
Shoulda::Matchers.configure do |config|
    config.integrate do |with|
      with.test_framework :rspec
      with.library :rails
    end
end
``` 
  - we're telling the shoulda-matcher gem to use RSpec as the test framework
and Rails full matcher libraries, which includes the active record, active
model and action controller libraries
 
9) we don't have to configure the factory_bot gem if we preface factory_bot methods
with `FactoryBot`
* however, if you don’t want to do this, inside the RSpec.configure​ block in `spec/rails_helper.rb`​ add:

  `config.include FactoryBot::Syntax::Methods`

  - this allows you to call syntax methods without the FactoryBot preface <br /> for example: `build(:model)` vs `FactoryBot.build(:model)`

And that's it! Yae!!! In another blog I will walk you through how to use factory_bot​and faker to generate test data and also write a few model test.

References: <br />
*https://scotch.io/tutorials/build-a-restful-json-api-with-rails-5-part-one*<br />
*https://github.com/DatabaseCleaner/database_cleaner*<br />
*https://github.com/thoughtbot/factory_bot_rails*

