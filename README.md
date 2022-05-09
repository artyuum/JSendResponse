# JSendResponse
JSendResponse component for [HttpFoundation](https://github.com/symfony/http-foundation) based applications (Symfony, Silex, Laravel, Drupal, etc.). It follows the [JSend](https://github.com/omniti-labs/jsend) specification, allowing you to give consistent JSON responses to your users.

**Note**: This repository is a maintened fork of [Junker/JSendResponse](https://github.com/Junker/JSendResponse). See the [changelog](#changelog) for modification history.


## Installation
The best way to install JSendResponse is to use a [Composer](https://getcomposer.org/download):

    composer require artyuum/symfony-jsend-response

## Examples

```php
use Junker\JSendResponse\JSendResponse;
use Junker\JSendResponse\JSendSuccessResponse;
use Junker\JSendResponse\JSendFailResponse;
use Junker\JSendResponse\JSendErrorResponse;


class AppController
{
	...

	$data = ['id' => 50, 'name' => 'Waldemar'];
	$message = 'Error, total error!';
	$code = 5;

	return new JSendResponse(JSendResponse::STATUS_SUCCESS, $data);
	// or
	return new JSendResponse(JSendResponse::STATUS_FAIL, $data);
	// or 
	return new JSendResponse(JSendResponse::STATUS_ERROR, NULL, $message);
	// or
	return new JSendResponse(JSendResponse::STATUS_ERROR, $data, $message, $code);
	// or
	return new JSendSuccessResponse($data);
	// or
	return new JSendFailResponse($data);
	// or
	return new JSendErrorResponse($message);
	// or
	return new JSendErrorResponse($message, $code, $data);

}

```

## Changelog
This library follows [semantic versioning](https://semver.org).

* **1.1.0**
  * Replaced "junker/symfony-jsend-response" (<= 0.3.1) in composer.json (thanks [@alexdmccabe](https://github.com/alexdmccabe))

* **1.0.0**
  * The default HTTP status code when using JSendFailResponse is now 400.
  * The default HTTP status code when using JSendErrorResponse is now 500.
  * Removed support for Symfony 2 & 3.
  * Replaced usage of ArrayObject by a traditional array.
  * Now throwing an exception when trying to set a code to the wrong JSend status
  * Now throwing an exception when trying to set a message to the wrong JSend status
  * Renamed the "JsendResponse" folder to "JSendResponse" for consistency
  * Renamed constants name in JSendResponse
  * Tests

## Contributing
If you'd like to contribute, please fork the repository and make changes as you'd like. Be sure to follow the same coding style & naming used in this library to produce a consistent code.
