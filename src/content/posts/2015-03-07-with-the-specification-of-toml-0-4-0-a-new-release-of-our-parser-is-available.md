---
author: victor
excerpt: ''
categories:
    - PHP
tags: {  }
permalink: /with-the-specification-of-toml-0-4-0-a-new-release-of-our-parser-is-available
no_html_extension: true
layout: post
title: 'With the specification of TOML 0.4.0 a new release of our parser is available'
thumb_img: tools.png
header_img:
  url: "header-toml.jpg"
---
[The specification 0.4.0 of TOML](https://github.com/toml-lang/toml/blob/master/versions/en/toml-v0.4.0.md)
is out with new features such as literal strings or inline tables. In consecuence,
a new release of [our parser is available](https://github.com/yosymfony/Toml)
with a complete support for the latest specificaction:

* Allows underscores in numbers.
* Inline tables.

Changes produced in our parser since the [specificaction 0.2.0](https://github.com/toml-lang/toml/releases/tag/v0.2.0):

* Multiline strings.
* Literal strings.
* Multiline literal strings.
* Date format updated.

TomlBuilder has support for literal string:

```php
use Yosymfony\Toml\TomlBuilder;

$tb = new TomlBuilder();
$tb->addValue('literal', '@<\i\c*\s*>')
```

Literal strings must begin with '@'. This character indicates to TomlBuilder
that the string must be trated as literal.

There is a [chat room on Gitter](https://gitter.im/yosymfony/Toml) for
talking about this library.

Enjoy it!
