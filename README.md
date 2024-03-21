![Logo](https://banners.beyondco.de/Laravel%20Local%20Disk%20Temporary%20URL.png?theme=light&packageManager=composer+require&packageName=iritesh377%2Flaravel-local-temporary-url&pattern=rails&style=style_1&description=Integrate+temporary+URL+support+for+local+filesystem+drivers.&md=1&showWatermark=0&fontSize=100px&images=link)

## Installation

You can install the package via composer:

```bash
composer require iritesh377/laravel-local-temporary-url
```

You can publish the config file with:

```bash
php artisan vendor:publish --tag="local-temporary-url-config"
```

This is the contents of the published config file:

```php
return [
    'disk' => ['local'],

    'middleware' => ['web', 'signed']
];
```

## Usage

### Configuration
This package requires no configuration; simply install it and it's ready to use. However, if you wish to utilize a different local disk or add additional disks, configuration options are available. Multiple local disks can be configured using the `disk` key. <br>

By default, the package applies `web` and `signed` middleware on routes. Nevertheless, you have the flexibility to configure middleware(s) by using the `middleware` key.

### Generate Temporary URL
Temporary URLs can be generated using the same syntax as for the S3 disk.
```php
Storage::disk('local')->temporaryUrl('file.txt', now()->addMinutes(5));
```

## Testing

```bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.


## Credits

- [Ritesh Sapkota](https://github.com/iritesh377)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
