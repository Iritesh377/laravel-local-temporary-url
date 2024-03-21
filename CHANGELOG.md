# Changelog

This document records all significant changes made to `laravel-local-temporary-url`.

## First release  - 2024-03-21
Incorporated Laravel 11 compatibility.

### Usage

This package requires no configuration; simply install it and it's ready to use. However, if you wish to utilize a different local disk or add additional disks, configuration options are available. Multiple local disks can be configured using the `disk` key. <br>

By default, the package applies `web` and `signed` middleware on routes. Nevertheless, you have the flexibility to configure middleware(s) by using the `middleware` key.


#### Generate Temporary URL

Temporary URLs can be generated using the same syntax as for the S3 disk.

```php
Storage::disk('local')->temporaryUrl('file.txt', now()->addMinutes(5));


```