# Payscel PHP Library

This library provides a simple interface for interacting with the Payscel payment gateway in your PHP applications.

Installation
Using Composer:

```
composer require payscel/payscel
```
## Usage
Instantiate the Payscel class:
```php
require_once 'vendor/autoload.php';

use UnityArray\Payscel;

$apiKey = 'YOUR_API_KEY';
$linkId = 'YOUR_LINK_ID';
$payscel = new Payscel($apiKey, $linkId);

```

Initiate a payment:

```php
$msisdn = '254712345678'; // Phone number without the leading '+'
$amount = 10; // Amount in kes
$callback = 'https://your-website.com/callback'; // Your callback URL

$response = $payscel->initiate($msisdn, $amount, $callback);

// Handle the response (usually a JSON object containing checkout details)
```

Query the status of a payment:

```php

$checkoutId = 'CHECKOUT_ID_FROM_INITIATE_RESPONSE';

$response = $payscel->query($checkoutId);

// Handle the response (usually a JSON object containing payment status)
```
### Methods
- initiate($msisdn, $amount, $callback): Initiates a payment.
- query($checkoutId): Queries the status of a payment.

### Examples
Please see the examples directory for more detailed usage examples.

### Contributing
We welcome contributions! Please see the CONTRIBUTING.md file for more information.

### License
This library is licensed under the MIT License. See the LICENSE file for more information.