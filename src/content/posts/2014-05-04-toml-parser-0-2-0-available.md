---
author: victor
excerpt: ''
categories:
    - PHP
tags:
    - parser
    - toml
permalink: /toml-parser-0-2-0-available
no_html_extension: true
layout: post
title: 'Toml parser 0.2.0 available'
thumb_img: doc.png
header_img:
  url: "header-toml.jpg"
---
The new version of [TOML parser](https://github.com/yosymfony/Toml) has
support for [TOML specification 0.2.0](https://github.com/toml-lang/toml/releases/tag/v0.2.0).
The main changes of this specificaction are the **new array of tables** and the
**use of "table" instead of "key group" in terminology**.

Now, [**TomlBuilder**](https://github.com/yosymfony/Toml#tomlbuilder) has support
for creates tables and array of tables. **The method `addKeyGroup` was declared as deprecated and replaced by `addTable`**.
