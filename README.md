# PHP javascript obfuscator

<p align="center">
<a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-lightgrey.svg" alt="License"></a>
<a href="https://packagist.org/packages/octha/obfuscator"><img src="https://img.shields.io/packagist/v/octha/obfuscator" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/octha/obfuscator"><img src="https://img.shields.io/packagist/dt/octha/obfuscator" alt="Total Downloads"></a>
</p>

Protect your javascript source code with the simplest and fastest way to obfuscate javascript with PHP.

## Installation

```bash
composer require octha/obfuscator
```

## Usage

### Simple usage to obfuscate JS code

```php
$jsCode = "alert('Hello world!');"; //Simple JS code
$hunter = new \Octha\Obfuscator\Factory($jsCode); //Initialize with JS code in parameter
$obsfucated = $hunter->Obfuscate(); //Do obfuscate and get the obfuscated code
echo "<script>" . $obsfucated . "</script>";
```

### Simple usage to obfuscate HTML code

```php
$htmlCode = "<h1>Title</h1><p>Hello world!</p>"; //Simple HTML code
$hunter = new \Octha\Obfuscator\Factory($htmlCode, true); //Initialize with HTML code in first parameter and set second one to TRUE
$obsfucated = $hunter->Obfuscate(); //Do obfuscate and get the obfuscated code
echo "<script>" . $obsfucated . "</script>";
```

> **Note**: If your HTML code contains any JS codes please remove any comments in that js code to prevent issues.

### Set expiration time

```php
$hunter->setExpiration('+10 day'); //Expires after 10 days
$hunter->setExpiration('Next Friday'); //Expires next Friday
$hunter->setExpiration('tomorrow'); //Expires tomorrow
$hunter->setExpiration('+5 hours'); //Expires after 5 hours
$hunter->setExpiration('+1 week 3 days 7 hours 5 seconds'); //Expires after +1 week 3 days 7 hours and 5 seconds
```

### Domain name lock

```php
$hunter->addDomainName('google.com'); //the generated code will work only on google.com
```

> **Note**: you can add multiple domains by adding one by one.

## License

This package is licensed under the [MIT license](LICENSE) © [Octha](https://octha.com).
