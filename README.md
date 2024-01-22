# JSendResponse
JSendResponse component for [HttpFoundation](https://github.com/symfony/http-foundation) based applications (Symfony, Silex, Laravel, Drupal, etc.). It follows the [JSend](https://github.com/omniti-labs/jsend) specification, allowing you to give consistent JSON responses to your users.

**Note**: This repository is a <ins>maintened</ins> fork of [Junker/JSendResponse](https://github.com/Junker/JSendResponse). See the [releases page](https://github.com/artyuum/JSendResponse/releases) for modification history.


## Requirements
- PHP ^7.4 || ^8.0
- Symfony ^5.0 || ^6.0 || ^7.0

## Installation
The best way to install JSendResponse is to use a [Composer](https://getcomposer.org/download):

```
composer require artyuum/symfony-jsend-response
```

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


## Contributing
If you'd like to contribute, please fork the repository and make changes as you'd like. Be sure to follow the same coding style & naming used in this library to produce a consistent code.
