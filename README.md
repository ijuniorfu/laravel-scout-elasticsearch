# Laravel Scout Elasticsearch Driver

This package makes is the [Elasticsearch](https://www.elastic.co/products/elasticsearch) driver for Laravel Scout.

## Contents

- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Installation

You can install the package via composer:

``` bash
composer require ijuniorfu/laravel-scout-elasticsearch
```

You must add the Scout service provider and the package service provider in your app.php config:

```php
// config/app.php
'providers' => [
    ...
    Laravel\Scout\ScoutServiceProvider::class,
    ...
    ScoutEngines\Elasticsearch\ElasticsearchProvider::class,
],
```

### Setting up Elasticsearch configuration
You must have a Elasticsearch server up and running with the index you want to use created

If you need help with this please refer to the [Elasticsearch documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)

After you've published the Laravel Scout package configuration:

```php
// config/scout.php
// Set your driver to elasticsearch
    'driver' => env('SCOUT_DRIVER', 'elasticsearch'),

...
    'elasticsearch' => [
        'type' => env('ELASTICSEARCH_TYPE', '_doc'),
        'hosts' => [
            env('ELASTICSEARCH_HOST', 'http://localhost'),
        ],
    ],
...
```

## Usage

Now you can use Laravel Scout as described in the [official documentation](https://laravel.com/docs/5.6/scout)


## License

The MIT License (MIT).
