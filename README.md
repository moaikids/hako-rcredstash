# Hako::EnvProviders::Rcredstash
Provide variables from [rcredstash](https://github.com/adorechic/rcredstash) to [hako](https://github.com/eagletmt/hako)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'hako-rcredstash'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install hako-rcredstash

## Usage

1. Put encrypted value using rcredstash

```
$ rcredstash put encrypted.some_password 
secret value> veryverysecret
$ rcredstash get encrypted.some_password 
veryverysecret
```

2. Setting hako and run it
```
  env:
    $providers:
      - type: rcredstash
    SOME_PASSWORD: ‘#{encrypted.some_password}'
```

3. A value is set for the ECS environment variable

```
Environment Variables
Key Value
SOME_PASSWORD   veryverysecret
```


