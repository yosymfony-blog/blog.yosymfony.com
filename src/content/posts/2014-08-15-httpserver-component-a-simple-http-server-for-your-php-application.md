---
author: victor
excerpt: ''
categories:
    - PHP
tags:
    - http
    - react
    - server
permalink: /http-server-for-php
no_html_extension: true
layout: post
title: 'HttpServer component: a simple HTTP Server for your PHP application'
thumb_img: server.png
header_img:
  url: "header-code.png"
  author: "Yuri Samoilov"
  author_url: "https://flic.kr/p/mjhDwB"
---
I'm currently working on a built-in server for [Spress](http://spress.yosymfony.com),
a simple HTTP server for watching changes in files without run `spress site:build`
command every time you make a change. [**HttpServer**](https://github.com/yosymfony/HttpServer) is
a small server built with [REACT](http://reactphp.org/), the event-driven and non-blocking
I/O library for PHP.

The installation is straightforward thanks to [Composer](https://getcomposer.org/) tool:
add the following to your `composer.json` file:

```json
"require": {
    "yosymfony/httpserver": "1.0.x-dev"
}
```

An example of how to use:

```php
$requestHandler = new RequestHandler(function($request) {
    return 'Hi Yo! Symfony';
});

$server = new HttpServer($requestHandler);
$server->start();

// go to http://localhost:8080
```

`RequestHandler` let you configure params such as port or host for
managing requests. The constructor only expects a single
[callable](http://php.net/manual/en/language.types.callable.php) type argument.
That is a function to handle each request.

### The handler function

The handler function receives a single parameter to describe the request.
By default, this argument is a
object type [React\Http\Request](https://github.com/reactphp/http/blob/master/src/Request.php).
If you want to receive a [Symfony HttpFoundation Request](http://symfony.com/doc/current/components/http_foundation/introduction.html#request)
object, you need to enable this mode: `$requestHandler->enableHttpFoundationRequest()`.

### Configuring the response

By default, the `Content-Type` value is `text/plain` at the response header and
a simple `return 'your text';` works fine but you can customize your response
with [status code and custom headers attributes](https://github.com/yosymfony/HttpServer#the-response).

### A complete example

This example point out how to use an array response:

```php
include_once __DIR__ . '/vendor/autoload.php';

use Yosymfony\HttpServer\HttpServer;
use Yosymfony\HttpServer\RequestHandler;

$requestHandler = new RequestHandler(function($request) {
   return [
      'content' => '<?xml version="1.0" encoding="UTF-8"?><root>Hi</root>',
      'headers' => ['Content-Type' => 'text/xml'],
      'status_code' => 200
   ];
});

$requestHandler->listen(8080)->enableHttpFoundationRequest();

$server = new HttpServer($requestHandler);
$server->start();
```

Nice coding ;)
