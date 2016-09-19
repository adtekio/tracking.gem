# Tracking Gem

Gem for generating example in-app tracking events.

Supported events can be found [here](/lib/adtekio_tracking/events.rb). But
there these can be extended with new events however correspondingly,
need to extend [consumers](https://github.com/adtekio/consumers) to use new
events.

## Using

In the gemfile:

```
gem 'adtekio_tracking', :git => 'https://github.com/adtekio/tracking.gem.git'
```

Then install using bundler

```
bundle
```

Configuration is then:

```
require 'adtekio_tracking'

AdtekioTracking.configure do |config|
  config.endpoint = ENV['TRACKING_HOST']
end
```

as found [here](https://github.com/adtekio/consumers/blob/master/config/initializers/adtekio_tracking.rb).

To trigger an event:

```
AdtekioTracking::Events.new.
  install({:click => click.payload, :install => event.payload})
```

as found [here](https://github.com/adtekio/consumers/blob/master/lib/consumers/attribution.rb#L49-L50).

## Travis

[![Build Status](https://travis-ci.org/adtekio/tracking.gem.svg?branch=master)](https://travis-ci.org/adtekio/tracking.gem)
