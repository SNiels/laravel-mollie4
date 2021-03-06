# laravel-mollie4

This is a package to integrate [Mollie](https://github.com/mollie/mollie-api-php) with Laravel 4.
You can use it to easily manage your configuration, and use the Facade to provide shortcuts to the Mollie Client.
This package is based on [laravel-mollie](https://github.com/EBOOST/laravel-mollie) by [EBOOST](https://github.com/EBOOST) for Laravel 5.

## Install

Via Composer

``` bash
$ composer require sniels/laravel-mollie4
```

## Installation

Via Composer

    $ composer require sniels/laravel-mollie4

After updating composer, add the LaravelMollieServiceProvider to the providers array in config/app.php

    Sniels\LaravelMollie\LaravelMollieServiceProvider::class,

You need to publish the config for this package. A sample configuration is provided. The defaults will be merged with gateway specific configuration.

    $ php artisan config:publish sniels/laravel-mollie4

To use the Facade (`\Mollie::getMethods()` instead of `App::make('mollie')->getMethods()`), add that to the facades array.

     'Mollie' => Sniels\LaravelMollie\Facades\Mollie::class,


## Examples
``` php
    // List Methods
    $methods = \Mollie::getMethods()->all();

    foreach ($methods as $method)
    {
        echo '<div style="line-height:40px; vertical-align:top">';
        echo '<img src="' . htmlspecialchars($method->image->normal) . '"> ';
        echo htmlspecialchars($method->description);
        echo ' (' .  htmlspecialchars($method->id). ')';
        echo '</div>';
    }
```

## Credits
- [EBOOST][https://github.com/EBOOST]
- [Bert van Hoekelen][https://github.com/BertvanHoekelen]