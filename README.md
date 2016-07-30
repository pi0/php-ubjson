# PHP-UBJSON
[![Packagist](https://img.shields.io/packagist/l/fandogh/php-ubjson.svg)](https://packagist.org/packages/fanndogh/php-ubjson)
[![Packagist](https://img.shields.io/packagist/v/fandogh/php-ubjson.svg)](https://packagist.org/packages/fandogh/php-ubjson)

A library to read and write to the [Universal Binary JSON](http://ubjson.org/ "ubjson.org") (Draft 9) format using PHP

# Install using composer

Using command line:
```bash 
composer require fandogh/php-ubjson
```

Or add this to your `composer.json` file:
```js
"require": {
  ...
  "fandogh/php-ubjson": "^0.2.2",
  ...
}
```

# Usage

PLEASE NOTE THAT ENCODED RESULT IS A BINARY STRING and some charachters are non printable!!

```php
// Don't forget to require autoload.php with correct path
require './vendor/autoload.php';

// Test data
$payload = ['hello'=>123];

// Encode using UBJSON
$encoded = \UBJSON::encode($payload); //string(24)  or 

# Incorrect! 
echo($encoded); // "{SUhelloU{}" 
# Correct!
var_dump(bin2hex($encoded)); // "7b53550568656c6c6f557b7d"

// Test decoding
$decoded = \UBJSON::decode($encoded);
var_dump($decoded); // array(1) { ["hello"]=> int(123) }

```


# Licence

This code is distributed under BSD license.
