![example workflow](https://github.com/df3g/simple-php-router/actions/workflows/tests.yml/badge.svg)

# Lightweight PHP MVC Router

A simple, framework-agnostic PHP MVC router for easy routing in PHP applications.

## Features

- Lightweight and dependency-free
- Supports dynamic route parameters
- Flexible route handling
- Easy to integrate
- Customizable 404 handling

## Installation

Install via Composer:

```bash
composer require df3g/simple-php-router
```

## Basic Usage

```php
<?php
use Df3g\Router\Request;
use Df3g\Router\Router;

// Create a new router instance
$router = new Router();

// Define routes
$router->addRoute('GET', '/', function() {
    echo "Home Page";
});

$router->addRoute('GET', '/users/{id}', function(Request $request) {
    echo "User Profile for ID:". $request->getParam('id');
});

// Dispatch the current request
$router->dispatch();
```

## Advanced Usage

### Custom 404 Handler

```php
$router->set404Handler(function() {
    http_response_code(404);
    echo "Page not found";
});
```


## Tests


### Run all tests
```bash
./vendor/bin/phpunit
```

### Run specific test
```bash
./vendor/bin/phpunit tests/RouterTest.php
```
### Generate code coverage report
```bash
./vendor/bin/phpunit --coverage-html coverage
```

## License

MIT License