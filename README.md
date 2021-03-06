# Webhook

[![Code Climate](https://codeclimate.com/github/AbleTech/webhook.png)](https://codeclimate.com/github/AbleTech/webhook)
[![Build Status](https://secure.travis-ci.org/AbleTech/webhook.png)](http://travis-ci.org/AbleTech/webhook)

Client library for making webhook calls. Compatible with Ruby 1.8.7, 1.9.2, 1.9.3, 2.0.0, 2.1.0, 2.2.0, REE, JRuby 1.8 and 1.9.

There are no runtime dependencies.

## Installation

Add this line to your application's Gemfile:

    gem 'webhook', '~> 1.0.0'

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install webhook

## Usage

    require 'webhook'

    code, message, body = Webhook.post('http://requestb.in/yadzsfya', :name => 'Abletech', :age => '6')

    if code == '200'
      puts "Success: #{body}"
    else
      puts "Error (#{code}): {message}\n#{body}"
    end

### Basic Authentication

If your webhook endpoint requires HTTP basic authentication, you can embed these in the supplied URL.
For example:

    Webhook.post('http://myusername:mypassword@requestb.in/jdhdyfhd')

## Configuration

You can configure your webhook using the following block. If you are using Rails, you would
normally add this code block in `config/initializers/webhook.rb`

    Webhook.configure do |config|
      config.user_agent = "My Application"
    end

## Testing

    rake spec

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
