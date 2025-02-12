# NBG Currency

[![Build Status](https://travis-ci.org/Masmaleki/nbg-currency.svg?branch=master)](https://travis-ci.org/Masmaleki/nbg-currency) [![Latest Stable Version](https://img.shields.io/packagist/v/Masmaleki/nbg-currency.svg)](https://packagist.org/packages/masmaleki/nbg-currency) [![Total Downloads](https://img.shields.io/packagist/dt/Masmaleki/nbg-currency.svg)](https://packagist.org/packages/masmaleki/nbg-currency)

National Bank of Georgia (NBG) currency service API wrapper in PHP with new wsdl service

## Installation

Install this package via [Composer](https://getcomposer.org/).

```
composer require masmaleki/nbg-currency
```

> Note: **PHP 7.1.8 or later** is required. For older versions, use `^1.2` version of this package.

## Usage

The class is namespaced as `Masmaleki\NbgCurrency\NbgCurrency`, so use it like

```php
use Masmaleki\NbgCurrency\NbgCurrency;
```

This package is very easy to use and has a few methods. **Keep in mind that method names are not same as NBG's SOAP service.** This package has more intuitive method names.

In addition, currencies are **not** case-sensitive here.

### Methods

##### `rate($currency)`

Get the currency rate.

```php
$currencies = 'USD,EUR';
$result = NbgCurrency::rate($currencies);
 foreach($result->GetCurrentRatesResult->CurrencyRate as $rate) {
    
            echo " --------------------\n";
            echo "Quantity: " . $rate->Quantity . "\n";
            echo "Rate:     " . floatval($rate->Rate) . "\n";
            echo "Diff:     " . floatval($rate->Diff) . "\n";
            echo "Code:     " . $rate->Code . "\n";
            echo "Name:     " . $rate->Name . "\n";
            echo "Date:     " . $rate->Date . "\n";
            echo "ValidFrom:     " . $rate->ValidFromDate . "\n"; 
    }
  
```


##### `isSupported($currency)`

Check if the currency is supported.

```php
NbgCurrency::isSupported('usd'); // true
NbgCurrency::isSupported('lol'); // false
```




### Keywords

> ლარის კურსი, ეროვნული ბანკის გაცვლითი კურსი, ვალუტა, ლარის ვალუტის კურსი, laris kursi, laris valuta, lari currency, national bank of georgia, nbg
### Thank you 
>Thanks of Levan Velijanashvili Nbg-Currency Package "Stichoza/nbg-currency"