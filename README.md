# A simple php Discogs Api Wrapper.

[![Latest Version on Packagist](https://img.shields.io/packagist/v/jolitagrazyte/discogs-api-wrapper.svg?style=flat-square)](https://packagist.org/packages/jolitagrazyte/discogs-api-wrapper)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/JolitaGrazyte/discogs-api-wrapper/master.svg?style=flat-square)](https://travis-ci.org/JolitaGrazyte/discogs-api-wrapper)
[![SensioLabsInsight](https://img.shields.io/sensiolabs/i/xxxxxxxxx.svg?style=flat-square)](https://insight.sensiolabs.com/projects/xxxxxxxxx)
[![Quality Score](https://img.shields.io/scrutinizer/g/JolitaGrazyte/discogs-api-wrapper.svg?style=flat-square)](https://scrutinizer-ci.com/g/JolitaGrazyte/discogs-api-wrapper)
[![Total Downloads](https://img.shields.io/packagist/dt/jolitagrazyte/discogs-api-wrapper.svg?style=flat-square)](https://packagist.org/packages/jolitagrazyte/discogs-api-wrapper)


This package makes it easy to communicate with discogs-api. It uses Guzzle6 and is very simple to install and to use.

You can use it with any php framework or just simply in your naked php application.

However if you want to use it in Laravel framework, i'd suggest to also install jolitagrazyte/laravel-discogs package, 
which provides a facade for even an easier way to play with it.

## Installation

You can install the package via composer:

``` bash
composer require jolitagrazyte/discogs-api-wrapper
```

## Usage

### Endpoints with no authentication required

For the endpoints, where token is not required, first argument can be easily left empty.
``` php
$discogs = new DiscogsApi('', 'app-name');

$artist = $discogs->artist('1');

$artistReleases = $discogs->artistReleases('1');

$label = $discogs->label('1');

$labelReleases = $discogs->labelReleases('1');

$releases = $discogs->releases('1');

$masterRelease = $discogs->masterRelease(string $id);
```

### Endpoints where authentication is required
For the endpoints, where token is require, you must add your disocgs-token.
You can get your token at https://www.discogs.com/settings/developers.

```php
$discogs = new DiscogsApi('disocgs-token', 'app-name');

$searchResult = $discogs->search('MoWax');

$orders = $discogs->getMyOrders();
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Security

If you discover any security related issues, please email hello@jolitagrazyte.com instead of using the issue tracker.

## Credits

- [Jolita Grazyte](https://github.com/JolitaGrazyte)
- [All Contributors](../../contributors)

## About Spatie
Spatie is a webdesign agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
