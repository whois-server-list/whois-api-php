# Domain API

This is a client library for the [Whois API service](http://whois-api.domaininformation.de/).
With this API you can

- Check if a domain name is available
- Get its whois data or query an arbitrary whois server
- Don't worry about rate limits on the respective whois server

The service supports all domains of the
[Whois Server list](https://github.com/whois-server-list/whois-server-list),
which is more than 500 top level domains.

# Installation

Use [Composer](https://getcomposer.org/):

```sh
composer require whois-server-list/whois-api
```

# Usage

You'll need an api key to use this library. Get one from 
the [Whois API](http://whois-api.domaininformation.de/).

```php
$whoisApi = new whoisServerList\WhoisApi("apiKey");
```

- [`WhoisApi::isAvailable()`](http://whois-server-list.github.io/whois-api-php/api/class-whoisServerList.WhoisApi.html#_isAvailable)
  checks if a domain name is available.
- [`WhoisApi::areAvailable()`](http://whois-server-list.github.io/whois-api-php/api/class-whoisServerList.WhoisApi.html#_areAvailable)
  checks multiple domain names if they are available.
- [`WhoisApi::whois()`](http://whois-server-list.github.io/whois-api-php/api/class-whoisServerList.WhoisApi.html#_whois)
  returns the whois data of a domain.
- [`WhoisApi::query()`](http://whois-server-list.github.io/whois-api-php/api/class-whoisServerList.WhoisApi.html#_query)
  queries an arbitrary whois server.
- [`WhoisApi::domains()`](http://whois-server-list.github.io/whois-api-php/api/class-whoisServerList.WhoisApi.html#_domains)
  Lists all top and second level domains which can be used by the Whois API.

## Example

```php
$whoisApi = new whoisServerList\WhoisApi("apiKey");
echo $whoisApi->isAvailable("example.net") ? "available" : "registered";
```

# License and authors

This project is free and under the WTFPL.
Responsable for this project is Markus Malkusch markus@malkusch.de.

[![Build Status](https://travis-ci.org/whois-server-list/whois-api-php.svg?branch=master)](https://travis-ci.org/whois-server-list/whois-api-php)
