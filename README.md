# Rack::Mixpanel [![Build Status](https://travis-ci.org/okcwest/rack-mixpanel.png?branch=master)](https://travis-ci.org/okcwest/rack-mixpanel)

Rack::Mixpanel provides a piece of Rack middleware for tracking events with
the same identity as set in the client-side JavaScript API. This is
achieved through parsing the cookie that Mixpanel sets on your site's
domain.

## Installation

Add this line to your application's Gemfile:

    gem 'rack-mixpanel', :require => 'rack/mixpanel'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install rack-mixpanel

### Rails

In your config/application.rb:

```
config.middleware.use Rack::Mixpanel
```

This will use the "MIXPANEL_API_TOKEN" environment variable as the
Mixpanel API token.

Alternatively, you may set this explicitly:

```
config.middleware.use Rack::Mixpanel, '54c0b5d418d4215a1061a894736eeed9'
```

## Usage

### Track events

```ruby
env['mixpanel.tracker'].track event_name, properties
```

Example:

```ruby
env['mixpanel.tracker'].track 'Sent message', {:age => 25,
:recipient_age => 23}
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Pick out an [emoji](http://www.emoji-cheat-sheet.com).
4. Commit your changes (`git commit -am ':new: Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create new Pull Request
